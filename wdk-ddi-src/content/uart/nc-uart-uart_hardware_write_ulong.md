---
UID: NC:uart.UART_HARDWARE_WRITE_ULONG
title: UART_HARDWARE_WRITE_ULONG (uart.h)
description: Writes a ULONG value to the specified port or register.
tech.root: serports
ms.assetid: 6c4f3758-dec5-4466-968d-f4eec9eee6bf
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_WRITE_ULONG callback function"]
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
 - UART_HARDWARE_WRITE_ULONG
 - uart/UART_HARDWARE_WRITE_ULONG
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_WRITE_ULONG
---

# UART_HARDWARE_WRITE_ULONG callback function


## -description

Writes a ULONG value to the specified port or register.

## -parameters

### -param Address

A pointer to a variable that contains the port or register address.

### -param Value

A ULONG value to be written to the port or register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_WRITE_ULONG UartHardwareWriteUlong;

// Definition

VOID UartHardwareWriteUlong
(
	PULONG Address
	ULONG Value
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the **WritePort32** or **WriteRegister32** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.

## -see-also

