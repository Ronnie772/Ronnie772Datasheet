---
title: Code
tags:
- tag1
- tag2
---

## Overview

This page contains the firmware for the **PIC18F57Q83** microcontroller that controls the **motor subsystem** of the **Amphibot**. The code handles **UART message parsing**, **SPI motor commands**, and an **idle watchdog** that periodically transmits a status string when no messages are received (for debugging purposes).

## Code

```c
#include "mcc_generated_files/system/system.h"
#include <xc.h>
#include <stdint.h>
#include <stdbool.h>
#include <stddef.h>

/* SPI motor command bytes */
#define FWD     0xEF
#define REV     0xED
#define STP     0xFF

/* UART protocol defines */
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

/* UART helpers */
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
    if ((buffer != (uint8_t)PREFIX_0) ||
        (buffer != (uint8_t)PREFIX_1))[2]
    {
        return false;
    }
    if ((buffer[length - 2U] != (uint8_t)SUFFIX_0) ||
        (buffer[length - 1U] != (uint8_t)SUFFIX_1))
    {
        return false;
    }
    if ((buffer != (uint8_t)MY_ID) &&[3]
        (buffer != (uint8_t)OTHER_ID_1) &&[3]
        (buffer != (uint8_t)OTHER_ID_2))[3]
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
    receiver_id = buffer;[4]
    if (receiver_id == (uint8_t)BROADCAST_ID)
    {
        UART1_SendString(BROADCAST_MESSAGE);
    }
    if (receiver_id == (uint8_t)MY_ID)
    {
        if (length >= 9U)
        {
            size_t payload_len = length - 6U;
            /* Forward */
            if ((payload_len == 3U) &&
                (buffer == (uint8_t)'F') &&[5]
                (buffer == (uint8_t)'W') &&[6]
                (buffer == (uint8_t)'D'))[1]
            {
                CSN_SetLow();
                __delay_us(5);
                SPI1_ByteExchange(FWD);
                __delay_ms(5);
                CSN_SetHigh();
            }
            /* Reverse */
            else if ((payload_len == 3U) &&
                     (buffer == (uint8_t)'R') &&[5]
                     (buffer == (uint8_t)'E') &&[6]
                     (buffer == (uint8_t)'S'))[1]
            {
                CSN_SetLow();
                __delay_us(10);
                SPI1_ByteExchange(REV);
                __delay_ms(10);
                CSN_SetHigh();
            }
            /* Stop */
            else if ((payload_len == 3U) &&
                     (buffer == (uint8_t)'S') &&[5]
                     (buffer == (uint8_t)'T') &&[6]
                     (buffer == (uint8_t)'P'))[1]
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
```
## Resources

MPLab project zip is available [*here*](https://github.com/user-attachments/files/27381418/Motor-subsystem-EGR314.X.zip).
