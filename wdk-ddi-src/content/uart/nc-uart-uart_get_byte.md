---
UID: NC:uart.UART_GET_BYTE
title: UART_GET_BYTE (uart.h)
description: Reads a data byte from the UART device.
tech.root: serports
ms.assetid: d0b97aa3-4e93-498d-8afc-44588fd21388
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "uart/UART_GET_BYTE"
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
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- uart.h
api_name:
- UART_GET_BYTE
product:
- Windows
targetos: Windows
---

# UART_GET_BYTE callback function

## -description

Reads a data byte from the UART device.

## -prototype

```cpp
//Declaration

UART_GET_BYTE UartGetByte;

// Definition

UART_STATUS UartGetByte
(
	PCPPORT Port
	PUCHAR Byte
)
{...}

```

## -parameters

### -param Port
[_Inout_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that contains the  address of the port object that describes the UART hardware.

### -param Byte:
[_Out_] A pointer to a variable that contains received byte.

## -returns

Returns [**UART_STATUS**](ne-uart-uart_status.md)-type value that indicates success or failure of the operation.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md).


## -see-also

[**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md)

[**_CPPORT**](ns-uart-_cpport.md)

[**UART_STATUS**](ne-uart-uart_status.md)
