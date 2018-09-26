---
UID: NF:dbgmodel.IDebugHostMemory.WritePointers
title: IDebugHostMemory::WritePointers
author: windows-driver-content
description: TBD
ms.assetid: 2173d16d-c22b-412e-8e46-d5cb64922239
ms.author: windowsdriverdev
ms.date: 09/18/2018
ms.topic: method
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostMemory.WritePointers
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostMemory::WritePointers


## -description

 Takes a number of pointers as held in unsigned 64-bit values, truncates them to the native pointer size of the target, and writes them into the address space of the target as defined by the inpassed context and location.

## -parameters

### -param context

### -param location

### -param count

### -param pointers


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)
