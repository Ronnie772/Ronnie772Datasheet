


#include "mcc_generated_files/system/system.h"
#include <xc.h>
#include <stdint.h>
#include <stdbool.h>
#include <stddef.h>

/* ?? SPI motor command bytes ?? */
#define FWD     0xEF
#define REV     0xED
#define STP     0xFF

/* ?? UART protocol defines ?? */
#define MY_ID               'R'
#define OTHER_ID_1          'M'
#define OTHER_ID_2          'L'
#define BROADCAST_ID        'X'

#define PREFIX_0            'A'
#define PREFIX_1            'Z'
#define SUFFIX_0            'Y'
#define SUFFIX_1            'B'

#define MAX_MESSAGE_BYTES   64U
#define MESSAGE_GAP_MS      2U
#define IDLE_TIMEOUT_MS     1000U

#define IDLE_MESSAGE        "..........."
#define MSG_TOO_LONG        "AZmessage too longYB"
#define BROADCAST_MESSAGE   "AZBroadcast msgYB"

/* ?? UART helpers ?? */
static void UART1_SendByte_Blocking(uint8_t data)
{
    while (!UART1_IsTxReady())
    {
    }
    UART1_Write(data);
}

static void UART1_SendString(const char *text)
{
    while (*text != '\0')
    {
        UART1_SendByte_Blocking((uint8_t)*text);
        text++;
    }
}

static bool MessageIsValid(const uint8_t *buffer, size_t length)
{
    if (length < 6U)
    {
        return false;
    }
    if ((buffer[0] != (uint8_t)PREFIX_0) ||
        (buffer[1] != (uint8_t)PREFIX_1))
    {
        return false;
    }
    if ((buffer[length - 2U] != (uint8_t)SUFFIX_0) ||
        (buffer[length - 1U] != (uint8_t)SUFFIX_1))
    {
        return false;
    }
    if ((buffer[2] != (uint8_t)MY_ID) &&
        (buffer[2] != (uint8_t)OTHER_ID_1) &&
        (buffer[2] != (uint8_t)OTHER_ID_2))
    {
        return false;
    }

  return true;
}

static bool UART1_ReadMessage(uint8_t *buffer, size_t *length)
{
    uint16_t gap_ms = 0U;
    size_t count = 0U;
    size_t uart_error;

   *length = 0U;

  while (1)
    {
        if (UART1_IsRxReady())
        {
            gap_ms = 0U;
      uart_error = UART1_ErrorGet();
            buffer[count] = UART1_Read();

//            if (uart_error != 0U)
//            {
//                count = 0U;
//                continue;
//            }
          count++;
            if (count >= MAX_MESSAGE_BYTES)
            {
                UART1_SendString(MSG_TOO_LONG);
              while (1)
                {
                    if (UART1_IsRxReady())
                    {
                        (void)UART1_ErrorGet();
                        (void)UART1_Read();
                        gap_ms = 0U;
                    }
                    else
                    {
                        __delay_ms(1);
                        gap_ms++;
                        if (gap_ms >= MESSAGE_GAP_MS)
                        {
                            *length = 0U;
                            return false;
                        }
                    }
                }
            }
        }
        else
        {
            if (count == 0U)
            {
                return false;
            }
          __delay_ms(1);
            gap_ms++;
            if (gap_ms >= MESSAGE_GAP_MS)
            {
                *length = count;
                return true;
            }
        }
    }
}

static void ProcessMessage(const uint8_t *buffer, size_t length)
{
    size_t i;
    uint8_t receiver_id;
    if (!MessageIsValid(buffer, length))
    {
        return;
    }
    receiver_id = buffer[3];
    if (receiver_id == (uint8_t)BROADCAST_ID)
    {
        UART1_SendString(BROADCAST_MESSAGE);
    }
    if (receiver_id == (uint8_t)MY_ID)
    {
        if (length >= 9U)
        {
            size_t payload_len = length - 6U;
            /* AZLRFWDYB or AZMRFWDYB ? forward */
            if ((payload_len == 3U) &&
                (buffer[4] == (uint8_t)'F') &&
                (buffer[5] == (uint8_t)'W') &&
                (buffer[6] == (uint8_t)'D'))
            {
                CSN_SetLow();
                __delay_us(5);
                SPI1_ByteExchange(FWD);
                __delay_ms(5);
                CSN_SetHigh();
            }
            /* AZLRRESYB or AZMRRESYB ? reverse */
            else if ((payload_len == 3U) &&
                     (buffer[4] == (uint8_t)'R') &&
                     (buffer[5] == (uint8_t)'E') &&
                     (buffer[6] == (uint8_t)'S'))
            {
                CSN_SetLow();
                __delay_us(10);
                SPI1_ByteExchange(REV);
                __delay_ms(10);
                CSN_SetHigh();
            }
            /* AZLRSTPYB or AZMRSTPYB ? stop */
            else if ((payload_len == 3U) &&
                     (buffer[4] == (uint8_t)'S') &&
                     (buffer[5] == (uint8_t)'T') &&
                     (buffer[6] == (uint8_t)'P'))
            {
                CSN_SetLow();
                __delay_us(5);
                SPI1_ByteExchange(STP);
                __delay_ms(5);
                CSN_SetHigh();
            }
        }
        return;
    }
    for (i = 0U; i < length; i++)
    {
        UART1_SendByte_Blocking(buffer[i]);
    }
}

void main(void)
{
    uint8_t message_buffer[MAX_MESSAGE_BYTES];
    size_t message_length;
    uint16_t idle_count_ms = 0U;

   SYSTEM_Initialize();
    UART1_Initialize();
    SPI1_Initialize();
    SPI1_Host_Open(HOST_CONFIG);
    CSN_SetHigh();
    PWM_SetLow();
    DIR1_SetLow();
    DIS_SetLow();
    __delay_ms(1000);
    INTERRUPT_GlobalInterruptEnable();
    while (1)
    {
        if (UART1_IsRxReady())
        {
            idle_count_ms = 0U;
            if (UART1_ReadMessage(message_buffer, &message_length))
            {
                ProcessMessage(message_buffer, message_length);
            }
        }
        else
        {
            __delay_ms(1);
            idle_count_ms++;
           if (idle_count_ms >= IDLE_TIMEOUT_MS)
            {
                UART1_SendString(IDLE_MESSAGE);
                idle_count_ms = 0U;
            }
        }
    }
}
