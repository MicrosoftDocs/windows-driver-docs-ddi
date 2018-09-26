---
UID: NF:dbgmodel.IDebugHostMemory.GetDisplayStringForLocation
title: IDebugHostMemory::GetDisplayStringForLocation
author: windows-driver-content
description: TBD
ms.assetid: c9b9c5d6-4c5f-49ea-949e-846ec4a8a874
ms.author: windowsdriverdev
ms.date: 09/18/2018
ms.topic: method
ms.keywords: IDebugHostMemory::GetDisplayStringForLocation, GetDisplayStringForLocation, IDebugHostMemory.GetDisplayStringForLocation, IDebugHostMemory::GetDisplayStringForLocation, IDebugHostMemory.GetDisplayStringForLocation
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
-	IDebugHostMemory.GetDisplayStringForLocation
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostMemory::GetDisplayStringForLocation


## -description

For a given location within the address space of the target as defined by context and location, convert the location to a displayable string (according to whatever format the host chooses).

If the "verbose" argument is true, the string conversion may be "more verbose"

## -parameters

### -param context

### -param location

### -param verbose

### -param locationName


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)
