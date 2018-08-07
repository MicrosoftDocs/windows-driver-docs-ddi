---
UID: NC:uart.UART_INITIALIZE_PORT
title: UART_INITIALIZE_PORT
author: windows-driver-content
description: Initializes or resets the UART hardware.
tech.root: serports
ms.assetid: f5691b9c-0c57-4333-adc3-dbbdfdc5ecb8
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
-	UART_INITIALIZE_PORT
product:
-	Windows
targetos: Windows
---

# UART_INITIALIZE_PORT callback function

## -description

Initializes or resets the UART hardware. This callback function is called before calling any other driver functions.

## -prototype

```
//Declaration

UART_INITIALIZE_PORT UartInitializePort;

// Definition

BOOLEAN UartInitializePort
(
	PCHAR LoadOptions
	PCPPORT Port
	BOOLEAN MemoryMapped
	UCHAR AccessSize
	UCHAR BitWidth
)
{...}

```

## -parameters

### -param LoadOptions
 [_In_opt_Optional _Null_terminated_] A null-terminated load option string.

### -param Port
[_Inout_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that is filled with information about port initialization.

### -param MemoryMapped
A boolean value that indicates whether the UART hardware is accessed through memory-mapped registers or legacy port I/O.

### -param AccessSize
An ACPI Generic Access Size value that indicates the type of bus access that should be performed when accessing the UART hardware.

### -param BitWidth
A a number that indicates the width of the UART registers.


## -returns

Returns TRUE if the port has been successfully initialized, FALSE otherwise.


## -remarks

Register your implementation of this callback function by setting the appropriate member of [**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md).


## -see-also

[**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md)

[**_CPPORT**](ns-uart-_cpport.md)