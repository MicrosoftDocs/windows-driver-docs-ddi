---
UID: NC:uart.UART_HARDWARE_READ_ULONG
title: UART_HARDWARE_READ_ULONG (uart.h)
description: Reads a ULONG value from the specified port or register.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_READ_ULONG callback function"]
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
 - UART_HARDWARE_READ_ULONG
 - uart/UART_HARDWARE_READ_ULONG
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_READ_ULONG
---

# UART_HARDWARE_READ_ULONG callback function


## -description

Reads a ULONG value from the specified port or register.

## -parameters

### -param Address

A pointer to a variable that contains the port or register address.

## -returns

Returns the ULONG value that is read from the specified port or register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_READ_ULONG UartHardwareReadUlong;

// Definition

ULONG UartHardwareReadUlong
(
	PULONG Address
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the **ReadPort32** or **ReadRegister32** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.

## -see-also

[**uart.h**](index.md)