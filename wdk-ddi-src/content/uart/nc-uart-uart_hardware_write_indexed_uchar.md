---
UID: NC:uart.UART_HARDWARE_WRITE_INDEXED_UCHAR
title: UART_HARDWARE_WRITE_INDEXED_UCHAR
author: windows-driver-content
description: Writes a byte to the specified port address.
ms.assetid: d40c35cf-b369-40cd-bf55-97ce6fe7288b
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
-	UART_HARDWARE_WRITE_INDEXED_UCHAR
product: Windows
targetos: Windows
---

# UART_HARDWARE_WRITE_INDEXED_UCHAR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UART_HARDWARE_WRITE_INDEXED_UCHAR UartHardwareWriteIndexedUchar; 

// Definition

VOID UartHardwareWriteIndexedUchar 
(
	PCPPORT Port
	 const UCHAR Index
	 const UCHAR Value
)
{...}

```

## -parameters

### -param Port
[_In_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that was received during port initialization.

### -param Index
A zero-based index for the port.

### -param Value
Specifies a byte to be written to the register.


## -returns



## -remarks

Register your implementation of this callback function by setting the appropriate member of the [**_CPPORT**](ns-uart-_cpport.md) structure.


## -see-also