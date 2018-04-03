---
UID: NC:uart.UART_GET_BYTE
title: UART_GET_BYTE
author: windows-driver-content
description: 
ms.assetid: d0b97aa3-4e93-498d-8afc-44588fd21388
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
-	UART_GET_BYTE
product: Windows
targetos: Windows
---

# UART_GET_BYTE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UART_GET_BYTE UartGetByte; 

// Definition

UART_STATUS UartGetByte 
(
	PCPPORT Port
	PUCHAR Byte
)
{...}

```

## -parameters

### -param Port: 
### -param Byte: 



## -returns

Returns UART_STATUS that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also