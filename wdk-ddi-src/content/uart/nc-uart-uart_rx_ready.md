---
UID: NC:uart.UART_RX_READY
title: UART_RX_READY (uart.h)
description: Determines whether there is data pending in the UART hardware.
tech.root: serports
ms.assetid: c0c52445-f45a-4032-9fee-af6206d77809
ms.date: 10/19/2018
keywords: ["UART_RX_READY callback function"]
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
 - UART_RX_READY
 - uart/UART_RX_READY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_RX_READY
---

# UART_RX_READY callback function


## -description

Determines whether there is data pending in the UART hardware.

## -parameters

### -param Port

[_Inout_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that contains the  address of the port object that describes the UART hardware.

## -returns

Returns TRUE if data is available, FALSE otherwise.

## -prototype

```cpp
//Declaration

UART_RX_READY UartRxReady;

// Definition

BOOLEAN UartRxReady
(
	PCPPORT Port
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md).

## -see-also

[**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md)

[**_CPPORT**](ns-uart-_cpport.md)

[**UART_STATUS**](ne-uart-uart_status.md)

