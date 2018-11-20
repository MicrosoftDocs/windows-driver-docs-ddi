---
UID: NF:dbgmodel.IDebugHostMemory2.ReadPointers
title: IDebugHostMemory2::ReadPointers
author: windows-driver-content
description: Reads a number of pointer sized objects from the address space of the target as defined by the inpassed context and location.
ms.assetid: 69e56a93-2387-44fc-b127-94b165d2cb51
ms.date: 09/28/2018
ms.topic: method
ms.keywords: IDebugHostMemory2::ReadPointers, ReadPointers, IDebugHostMemory2.ReadPointers, IDebugHostMemory2::ReadPointers, IDebugHostMemory2.ReadPointers
req.header: dbgmodel.h
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
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostMemory2.ReadPointers
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostMemory2::ReadPointers


## -description

Reads a number of pointer sized objects from the address space of the target as defined by the inpassed context and location.

Each read pointer is, if necessary, zero extended to 64-bits and returned.

## -parameters

### -param context
The host context in which to read pointers.  This represents, for example, the address space in which the location exists.

### -param location
The location at which to read pointers.  This location may represent a virtual address within the address space defined by context or it may represent something like a register within a context record for a thread.

### -param count
The number of pointers to read.

### -param pointers
The pointers read from the debug target will be placed into the array passed here.  Any pointers less than 64-bits in size will be zero extended to 64-bits.



## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory2 interface](nn-dbgmodel-idebughostmemory2.md)
