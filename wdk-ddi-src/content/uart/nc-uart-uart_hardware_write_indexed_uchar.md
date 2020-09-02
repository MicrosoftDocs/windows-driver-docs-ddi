---
UID: NC:uart.UART_HARDWARE_WRITE_INDEXED_UCHAR
title: UART_HARDWARE_WRITE_INDEXED_UCHAR (uart.h)
description: Writes a byte to the specified port address.
tech.root: serports
ms.assetid: d40c35cf-b369-40cd-bf55-97ce6fe7288b
ms.date: 10/19/2018
keywords: ["UART_HARDWARE_WRITE_INDEXED_UCHAR callback function"]
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
targetos: Windows
f1_keywords:
 - UART_HARDWARE_WRITE_INDEXED_UCHAR
 - uart/UART_HARDWARE_WRITE_INDEXED_UCHAR
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - uart.h
api_name:
 - UART_HARDWARE_WRITE_INDEXED_UCHAR
---

# UART_HARDWARE_WRITE_INDEXED_UCHAR callback function


## -description

Implemented by the client driver to ...

## -parameters

### -param Port

[_In_] A pointer to a [**_CPPORT**](ns-uart-_cpport.md) structure that was received during port initialization.

### -param Index

A zero-based index for the port.

### -param Value

Specifies a byte to be written to the register.

## -prototype

```cpp
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

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [**_CPPORT**](ns-uart-_cpport.md) structure.

## -see-also

