---
UID: NF:dbgmodel.IDebugHostMemory.ReadPointers
title: IDebugHostMemory::ReadPointers
author: windows-driver-content
description: TBD
ms.assetid: 8c1d7ea2-97cf-421c-ac85-9030eb6cf582
ms.author: windowsdriverdev
ms.date: 09/18/2018
ms.topic: method
ms.keywords: IDebugHostMemory::ReadPointers, ReadPointers, IDebugHostMemory.ReadPointers, IDebugHostMemory::ReadPointers, IDebugHostMemory.ReadPointers
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
-	IDebugHostMemory.ReadPointers
product: Windows
targetos: Windows


---

# IDebugHostMemory::ReadPointers


## -description

Reads a number of pointer sized objects from the address space of the target as defined by the inpassed context and location.

Each read pointer is, if necessary, zero extended to 64-bits and returned.

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