---
UID: NC:uart.UART_HARDWARE_READ_ULONG64
title: UART_HARDWARE_READ_ULONG64 (uart.h)
description: Reads a ULONG64 value from the specified register address.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_READ_ULONG64 callback function"]
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
 - UART_HARDWARE_READ_ULONG64
 - uart/UART_HARDWARE_READ_ULONG64
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_READ_ULONG64
---

# UART_HARDWARE_READ_ULONG64 callback function


## -description

Reads a ULONG64 value from the specified port address.

## -parameters

### -param Address

A pointer to the register address, which must be a mapped range in memory space.

## -returns

Returns ULONG64 that is read from the specified register address.

## -prototype

```cpp
//Declaration

UART_HARDWARE_READ_ULONG64 UartHardwareReadUlong64;

// Definition

ULONG64 UartHardwareReadUlong64
(
	PULONG64 Address
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the **ReadRegister64** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.

## -see-also

[**uart.h**](index.md)