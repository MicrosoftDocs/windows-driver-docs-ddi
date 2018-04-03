---
UID: NC:uart.UART_HARDWARE_READ_ULONG
title: UART_HARDWARE_READ_ULONG
author: windows-driver-content
description: 
ms.assetid: 242023e2-fae1-4d27-9175-3438a9ba3bac
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
-	UART_HARDWARE_READ_ULONG
product: Windows
targetos: Windows
---

# UART_HARDWARE_READ_ULONG callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UART_HARDWARE_READ_ULONG UartHardwareReadUlong; 

// Definition

ULONG UartHardwareReadUlong 
(
	PULONG Address
)
{...}

```

## -parameters

### -param Address: 



## -returns

Returns ULONG that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also