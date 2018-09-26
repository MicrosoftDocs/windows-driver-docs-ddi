---
UID: NF:dbgmodel.IDebugHostMemory2.WritePointers
title: IDebugHostMemory2::WritePointers
author: windows-driver-content
description: TBD
ms.assetid: ce3d732f-1245-4441-b880-e507dcbea189
ms.author: windowsdriverdev
ms.date: 09/18/2018 
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

[IDebugHostMemory2 interface](nn-dbgmodel-idebughostmemory2.md)
