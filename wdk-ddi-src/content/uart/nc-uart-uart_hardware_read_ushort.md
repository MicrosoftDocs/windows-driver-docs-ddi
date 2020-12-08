---
UID: NC:uart.UART_HARDWARE_READ_USHORT
title: UART_HARDWARE_READ_USHORT (uart.h)
description: Reads a USHORT value from the specified port or register.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_READ_USHORT callback function"]
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
 - UART_HARDWARE_READ_USHORT
 - uart/UART_HARDWARE_READ_USHORT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_READ_USHORT
---

# UART_HARDWARE_READ_USHORT callback function


## -description

Reads a USHORT value from the specified port or register.

## -parameters

### -param Address

A pointer to a variable that contains the port or register address.

## -returns

Returns USHORT that is read from the specified port or register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_READ_USHORT UartHardwareReadUshort;

// Definition

USHORT UartHardwareReadUshort
(
	PUSHORT Address
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the **ReadPort16** or **ReadRegister16** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.

## -see-also

