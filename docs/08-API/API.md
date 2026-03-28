---
title: API
tags:
- tag1
- tag2
---

## Overview
This document defines the UART message API for the Actuator. It includes all messages sent, received, and acted upon by the actuator subsystem. All messages follow the class communication protocol and only the message data portion is defined here.

## Message Type 0x0001 – Set Motor Speed

Direction: Received

Purpose: Command to set motor speed and direction.

| Field |	Byte 1–2 | Byte 3	| Byte 4–5 |
|-------|----------|--------|----------|
|Variable Name |	message_type |	direction |	target_speed_rpm |
| Variable Type | uint16_t | uint8_t | uint16_t |
| Min Value |	1 |	0 | 0 |
| Max Value	| 1	| 2	| 300 |
| Example	| 1	| 1	| 200 |

Number of bytes: 5

## Message Type 0x0004 – Motor Telemetry Response

Direction: Sent

Purpose: Reports motor state and current speed.

| Field |	Byte 1–2 | Byte 3	| Byte 4–5 |
|-------|----------|--------|----------|
|Variable Name |	message_type |	direction |	target_speed_rpm |
| Variable Type | uint16_t | uint8_t | uint16_t |
| Min Value |	4 |	0 | 0 |
| Max Value	| 4	| 2	| 300 |
| Example	| 4	| 1	| 200 |

Number of bytes: 5

## Message Type 0x0005 – Emergency Stop

Direction: Received / Acted on

Purpose: Immediately halts motor operation.

| Field |	Byte 1–2 |
|-------|----------|
|Variable Name |	message_type |
| Variable Type | uint16_t |
| Min Value |	5 |
| Max Value	| 5	|
| Example	| 5	|

Number of bytes: 2
