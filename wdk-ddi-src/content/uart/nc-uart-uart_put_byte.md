---
UID: NC:uart.UART_PUT_BYTE
title: UART_PUT_BYTE (uart.h)
description: Writes a data byte to the UART device.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_PUT_BYTE callback function"]
req.header: uart.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - UART_PUT_BYTE
 - uart/UART_PUT_BYTE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_PUT_BYTE
---

# UART_PUT_BYTE callback function


## -description

Writes a data byte to the UART device.

## -parameters

### -param Port

[_Inout_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that contains the  address of the port object that describes the UART hardware.

### -param Byte

The byte to write to the UART hardware.

### -param BusyWait

A flag to control whether this routine will busy-wait (spin) for the UART hardware to be ready to transmit.

## -returns

Returns [**UART_STATUS**](ne-uart-uart_status.md)-type value that indicates success or failure of the operation.

## -prototype

```cpp
//Declaration

UART_PUT_BYTE UartPutByte;

// Definition

UART_STATUS UartPutByte
(
	PCPPORT Port
	UCHAR Byte
	BOOLEAN BusyWait
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md).

## -see-also

[**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md)

[**_CPPORT**](ns-uart-_cpport.md)

[**UART_STATUS**](ne-uart-uart_status.md)

