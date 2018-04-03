---
UID: NC:uart.UART_PUT_BYTE
title: UART_PUT_BYTE
author: windows-driver-content
description: 
ms.assetid: d4db9a6d-b9ef-4b88-9f12-b4fe437eaa4b
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
-	UART_PUT_BYTE
product: Windows
targetos: Windows
---

# UART_PUT_BYTE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UART_PUT_BYTE UartPutByte; 

// Definition

UART_STATUS UartPutByte 
(
	PCPPORT Port
	UCHAR Byte
	BOOLEAN BusyWait
)
{...}

```

## -parameters

### -param Port: 
### -param Byte: 
### -param BusyWait: 



## -returns

Returns UART_STATUS that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also