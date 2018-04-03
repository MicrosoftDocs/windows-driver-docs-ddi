---
UID: NC:uart.UART_RX_READY
title: UART_RX_READY
author: windows-driver-content
description: 
ms.assetid: c0c52445-f45a-4032-9fee-af6206d77809
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
-	UART_RX_READY
product: Windows
targetos: Windows
---

# UART_RX_READY callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UART_RX_READY UartRxReady; 

// Definition

BOOLEAN UartRxReady 
(
	PCPPORT Port
)
{...}

```

## -parameters

### -param Port: 



## -returns

Returns BOOLEAN that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also