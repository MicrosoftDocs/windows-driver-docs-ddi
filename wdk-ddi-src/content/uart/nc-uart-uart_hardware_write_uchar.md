---
UID: NC:uart.UART_HARDWARE_WRITE_UCHAR
title: UART_HARDWARE_WRITE_UCHAR (uart.h)
description: Writes a byte to the port or a register.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_WRITE_UCHAR callback function"]
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
 - UART_HARDWARE_WRITE_UCHAR
 - uart/UART_HARDWARE_WRITE_UCHAR
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_WRITE_UCHAR
---

# UART_HARDWARE_WRITE_UCHAR callback function


## -description

Writes a byte to the port specified by address.

## -parameters

### -param Address

A pointer to a variable that contains the port or register address.

### -param Value

Specifies a byte to be written to the port or register.

## -prototype

```cpp
//Declaration

UART_HARDWARE_WRITE_UCHAR UartHardwareWriteUchar;

// Definition

VOID UartHardwareWriteUchar
(
	PUCHAR Address
	UCHAR Value
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the **WritePort8** or **WriteRegister8** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.

## -see-also

