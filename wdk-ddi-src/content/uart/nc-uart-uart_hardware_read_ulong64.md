---
UID: NC:uart.UART_HARDWARE_READ_ULONG64
title: UART_HARDWARE_READ_ULONG64
author: windows-driver-content
description: Reads a ULONG64 value from the specified register address.
tech.root: serports
ms.assetid: b94043dd-4c44-499c-8aee-6ce6f38f6310
ms.date:
ms.topic: callback
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
-	apiref
api_type:
-	UserDefined
api_location:
-	uart.h
api_name:
-	UART_HARDWARE_READ_ULONG64
product:
-	Windows
targetos: Windows
---

# UART_HARDWARE_READ_ULONG64 callback function

## -description

Reads a ULONG64 value from the specified port address.

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

## -parameters

### -param Address

A pointer to the register address, which must be a mapped range in memory space.


## -returns

Returns ULONG64 that is read from the specified register address.


## -remarks

Register your implementation of this callback function by setting the **ReadRegister64** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.


## -see-also
