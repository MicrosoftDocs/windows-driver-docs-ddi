---
UID: NC:uart.UART_HARDWARE_READ_UCHAR
title: UART_HARDWARE_READ_UCHAR (uart.h)
description: Reads a byte from the specified port or register.
tech.root: serports
ms.assetid: 1760bbfd-3995-4d32-81cc-c30c190aa465
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_READ_UCHAR callback function"]
f1_keywords:
 - "uart/UART_HARDWARE_READ_UCHAR"
 - "UART_HARDWARE_READ_UCHAR"
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
- UART_HARDWARE_READ_UCHAR
targetos: Windows
---

# UART_HARDWARE_READ_UCHAR callback function

## -description

Reads a byte from the specified port or register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_READ_UCHAR UartHardwareReadUchar;

// Definition

UCHAR UartHardwareReadUchar
(
	PUCHAR Address
)
{...}

```

## -parameters

### -param Address

A pointer to a variable that contains the port or register address.


## -returns

Returns the byte that is read from the specified port or register.

## -remarks

Register your implementation of this callback function by setting the **ReadPort8** or **ReadRegister8** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.


## -see-also
