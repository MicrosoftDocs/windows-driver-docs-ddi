---
UID: NC:uart.UART_HARDWARE_WRITE_ULONG64
title: UART_HARDWARE_WRITE_ULONG64
author: windows-driver-content
description: Writes a ULONG64 value to the specified register address.
tech.root: serports
ms.assetid: 28aa4d96-2798-44ba-b736-04df60fb098b
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UART_HARDWARE_WRITE_ULONG64
product:
-	Windows
targetos: Windows
---

# UART_HARDWARE_WRITE_ULONG64 callback function

## -description

Writes a ULONG64 value to the specified register address.

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

## -parameters

### -param Address
A pointer to the register, which must be a mapped range in memory space.

### -param Value
A ULONG64 value to be written to the register.


## -returns


## -remarks

Register your implementation of this callback function by setting the **WriteRegister64** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.


## -see-also
