---
UID: NC:uart.UART_HARDWARE_WRITE_ULONG64
title: UART_HARDWARE_WRITE_ULONG64 (uart.h)
description: Writes a ULONG64 value to the specified register address.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_WRITE_ULONG64 callback function"]
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
 - UART_HARDWARE_WRITE_ULONG64
 - uart/UART_HARDWARE_WRITE_ULONG64
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_WRITE_ULONG64
---

# UART_HARDWARE_WRITE_ULONG64 callback function


## -description

Writes a ULONG64 value to the specified register address.

## -parameters

### -param Address

A pointer to the register, which must be a mapped range in memory space.

### -param Value

A ULONG64 value to be written to the register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_WRITE_ULONG64 UartHardwareWriteUlong64;

// Definition

VOID UartHardwareWriteUlong64
(
	PULONG64 Address
	ULONG64 Value
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the **WriteRegister64** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.

## -see-also

