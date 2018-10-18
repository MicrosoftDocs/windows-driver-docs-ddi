---
UID: NC:uart.UART_HARDWARE_WRITE_UCHAR
title: UART_HARDWARE_WRITE_UCHAR
author: windows-driver-content
description: Writes a byte to the port or a register.
tech.root: serports
ms.assetid: 4fb781e3-0e25-4e35-8ebf-f8046b05fd23
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
-	UART_HARDWARE_WRITE_UCHAR
product:
-	Windows
targetos: Windows
---

# UART_HARDWARE_WRITE_UCHAR callback function

## -description

Writes a byte to the port specified by address.

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

## -parameters

### -param Address
A pointer to a variable that contains the port or register address.

### -param Value
Specifies a byte to be written to the port or register.



## -returns



## -remarks

Register your implementation of this callback function by setting the **WritePort8** or **WriteRegister8** member of the [**_UART_HARDWARE_ACCESS**](ns-uart-_uart_hardware_access.md) structure.


## -see-also
