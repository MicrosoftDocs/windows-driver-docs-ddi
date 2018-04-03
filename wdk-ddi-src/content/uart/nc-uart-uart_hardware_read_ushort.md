---
UID: NC:uart.UART_HARDWARE_READ_USHORT
title: UART_HARDWARE_READ_USHORT
author: windows-driver-content
description: 
ms.assetid: d516dfad-577b-4c6b-87df-ab6c7ce5c7f8
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
-	UART_HARDWARE_READ_USHORT
product: Windows
targetos: Windows
---

# UART_HARDWARE_READ_USHORT callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UART_HARDWARE_READ_USHORT UartHardwareReadUshort; 

// Definition

USHORT UartHardwareReadUshort 
(
	PUSHORT Address
)
{...}

```

## -parameters

### -param Address: 



## -returns

Returns USHORT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also