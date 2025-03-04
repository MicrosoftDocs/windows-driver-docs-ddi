---
UID: NF:dbgmodel.IDebugHostMemory5.GetDisplayStringForLocation
tech.root: debugger
title: IDebugHostMemory5::GetDisplayStringForLocation
ms.date: 02/24/2025
targetos: Windows
description: For a given location within the address space of the target as defined by context and location, convert the location to a displayable string (according to whatever format the host chooses).
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostMemory5::GetDisplayStringForLocation
f1_keywords:
 - IDebugHostMemory5::GetDisplayStringForLocation
 - dbgmodel/IDebugHostMemory5::GetDisplayStringForLocation
dev_langs:
 - c++
helpviewer_keywords:
 - GetDisplayStringForLocation
---

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

[IDebugHostMemory5 interface](nn-dbgmodel-idebughostmemory5.md)