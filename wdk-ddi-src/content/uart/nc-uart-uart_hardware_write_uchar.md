---
UID: NC:uart.UART_HARDWARE_WRITE_UCHAR
title: UART_HARDWARE_WRITE_UCHAR
author: windows-driver-content
description: 
ms.assetid: 4fb781e3-0e25-4e35-8ebf-f8046b05fd23
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
-	UART_HARDWARE_WRITE_UCHAR
product: Windows
targetos: Windows
---

# UART_HARDWARE_WRITE_UCHAR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

### -param Address: 
### -param Value: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also