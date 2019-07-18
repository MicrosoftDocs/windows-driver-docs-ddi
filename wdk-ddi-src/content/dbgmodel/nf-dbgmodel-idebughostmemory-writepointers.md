---
UID: NF:dbgmodel.IDebugHostMemory.WritePointers
title: IDebugHostMemory::WritePointers (dbgmodel.h)
description:  Takes a number of pointers as held in unsigned 64-bit values, truncates them to the native pointer size of the target, and writes them into the address space of the target as defined by the inpassed context and location.
ms.assetid: 2173d16d-c22b-412e-8e46-d5cb64922239
ms.date: 09/28/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostMemory.WritePointers"
ms.keywords: IDebugHostMemory::WritePointers, WritePointers, IDebugHostMemory.WritePointers, IDebugHostMemory::WritePointers, IDebugHostMemory.WritePointers
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostMemory.WritePointers
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostMemory::WritePointers


## -description

 Takes a number of pointers as held in unsigned 64-bit values, truncates them to the native pointer size of the target, and writes them into the address space of the target as defined by the inpassed context and location.

## -parameters

### -param context
The host context in which to write pointers.  This represents, for example, the address space in which the location exists.

### -param location
The location at which to write pointers.  This location may represent a virtual address within the address space defined by context or it may represent something like a register within a context record for a thread.

### -param count
The number of pointers to write.

### -param pointers
The pointers to write to the debug target.  If the target is 32-bits, the pointer values here will be truncated prior to writing them to the underlying debug target.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)
