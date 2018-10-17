---
UID: NC:uart.UART_SET_BAUD
title: UART_SET_BAUD
author: windows-driver-content
description: Changes the baud rate of the UART hardware.
tech.root: serports
ms.assetid: 1bce0489-47eb-4e27-b54c-6e920fde2039
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
-	UART_SET_BAUD
product:
-	Windows
targetos: Windows
---

# UART_SET_BAUD callback function

## -description

Changes the baud rate of the UART hardware.

## -prototype

```
//Declaration

UART_SET_BAUD UartSetBaud;

// Definition

BOOLEAN UartSetBaud
(
	PCPPORT Port
	ULONG Rate
)
{...}

```

## -parameters

### -param Port
[_Inout_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that contains the  address of the port object that describes the UART hardware.

### -param Rate:
The baud rate to set in bits per second.

## -returns

Returns TRUE if the baud rate was programmed, FALSE otherwise.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md).


## -see-also

[**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md)

[**_CPPORT**](ns-uart-_cpport.md)
