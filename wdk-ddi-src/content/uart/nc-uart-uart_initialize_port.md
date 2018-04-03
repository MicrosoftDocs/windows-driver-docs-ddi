---
UID: NC:uart.UART_INITIALIZE_PORT
title: UART_INITIALIZE_PORT
author: windows-driver-content
description: Initializes or resets the UART hardware. 
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
product: Windows
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

 
### -param Port
A bitwise of these flags:

- PORT_DEFAULT_RATE   0x0001
- PORT_RING_INDICATOR 0x0002
- PORT_MODEM_CONTROL  0x0004
- PORT_SAVED          0x0008
- PORT_FORCE_32BIT_IO 0x0010


### -param MemoryMapped

 
### -param AccessSize

 
### -param BitWidth



## -returns

Returns a BOOLEAN value ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**UART_HARDWARE_DRIVER**](ns-uart-_uart_hardware_driver.md).


## -see-also