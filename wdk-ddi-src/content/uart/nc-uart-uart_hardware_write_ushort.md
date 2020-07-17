---
UID: NC:uart.UART_HARDWARE_WRITE_USHORT
title: UART_HARDWARE_WRITE_USHORT (uart.h)
description: Writes a USHORT value to the specified port or register.
tech.root: serports
ms.assetid: f1ad2554-41ea-4db2-9547-09ee6c602a1e
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_WRITE_USHORT callback function"]
f1_keywords:
 - "uart/UART_HARDWARE_WRITE_USHORT"
 - "UART_HARDWARE_WRITE_USHORT"
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
- UART_HARDWARE_WRITE_USHORT
product:
- Windows
targetos: Windows
---

# UART_HARDWARE_WRITE_USHORT callback function

## -description

Writes a USHORT value to the specified port or register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_WRITE_USHORT UartHardwareWriteUshort;

// Definition

VOID UartHardwareWriteUshort
(
	PUSHORT Address
	USHORT Value
)
{...}

```

## -parameters

### -param Address
A pointer to a variable that contains the port or register address.

### -param Value
A USHORT value to be written to the port or register.


## -remarks

Register your implementation of this callback function by setting the appropriate member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.


## -see-also
