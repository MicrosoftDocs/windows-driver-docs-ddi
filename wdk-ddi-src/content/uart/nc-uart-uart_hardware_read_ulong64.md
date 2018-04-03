---
UID: NC:uart.UART_HARDWARE_READ_ULONG64
title: UART_HARDWARE_READ_ULONG64
author: windows-driver-content
description: 
ms.assetid: b94043dd-4c44-499c-8aee-6ce6f38f6310
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: uart.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
product: Windows
targetos: Windows
---

# UART_HARDWARE_READ_ULONG64 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

### -param Address: 



## -returns

Returns ULONG64 that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also