---
UID: NF:dbgmodel.IDebugHostMemory2.WritePointers
title: IDebugHostMemory2::WritePointers
author: windows-driver-content
description: Takes a number of pointers as held in unsigned 64-bit values, truncates them to the native pointer size of the target,and writes them into the address space of the target as defined by the inpassed context and location.
ms.assetid: ce3d732f-1245-4441-b880-e507dcbea189
ms.date: 09/28/2018 
ms.topic: method
ms.keywords: IDebugHostMemory2::WritePointers, WritePointers, IDebugHostMemory2.WritePointers, IDebugHostMemory2::WritePointers, IDebugHostMemory2.WritePointers
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
-	IDebugHostMemory2.WritePointers
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostMemory2::WritePointers


## -description

Takes a number of pointers as held in unsigned 64-bit values, truncates them to the native pointer size of the target,and writes them into the address space of the target as defined by the inpassed context and location.

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

[IDebugHostMemory2 interface](nn-dbgmodel-idebughostmemory2.md)
