---
UID: NF:dbgmodel.IDebugHostMemory2.GetDisplayStringForLocation
title: IDebugHostMemory2::GetDisplayStringForLocation (dbgmodel.h)
description: For a given location within the address space of the target as defined by context and location, convert the location to a displayable string (according to whatever format the host chooses).
ms.assetid: 0b7327dc-22ae-4bc3-b222-fa2f3210c453
ms.date: 09/28/2018
ms.topic: method
ms.keywords: IDebugHostMemory2::GetDisplayStringForLocation, GetDisplayStringForLocation, IDebugHostMemory2.GetDisplayStringForLocation, IDebugHostMemory2::GetDisplayStringForLocation, IDebugHostMemory2.GetDisplayStringForLocation
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
-	IDebugHostMemory2.GetDisplayStringForLocation
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostMemory2::GetDisplayStringForLocation


## -description

For a given location within the address space of the target as defined by context and location, convert the location to a displayable string (according to whatever format the host chooses).

If the "verbose" argument is true, the string conversion may be "more verbose"

## -parameters

### -param context
The host context in which the location is valid.  This represents, for example, the address space in which the location exists.

### -param location
The location to convert to a displayable string.

### -param verbose
An indication of whether the conversion should be verbose or not.  A verbose conversion will contain more information than a non-verbose one.  The default is for a non-verbose conversion.

### -param locationName
A displayable string for the location will be returned here.  This string is allocated by SysAllocString and the caller is responsible for freeing the allocation with a call to the SysFreeString function.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory2 interface](nn-dbgmodel-idebughostmemory2.md)
