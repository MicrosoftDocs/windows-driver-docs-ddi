---
UID: NF:dbgmodel.IDebugHostMemory5.LinearizeLocation
tech.root: debugger
title: IDebugHostMemory5::LinearizeLocation
ms.date: 02/24/2025
targetos: Windows
description: Takes a location which may represent something other than a virtual memory address and attempts to linearize the location into a virtual memory address within the given context.
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
 - IDebugHostMemory5::LinearizeLocation
f1_keywords:
 - IDebugHostMemory5::LinearizeLocation
 - dbgmodel/IDebugHostMemory5::LinearizeLocation
dev_langs:
 - c++
helpviewer_keywords:
 - LinearizeLocation
---

## -description

Takes a location which may represent something other than a virtual memory address and attempts to linearize the location into a virtual memory address within the given context.  This operation may fail if the location cannot be represented by a virtual address (e.g.: it's a register).

## -parameters

### -param context

The host context in which the location is valid.  This represents, for example, the address space in which the location exists.

### -param location

The location to linearize into a virtual memory address.

### -param pLinearizedLocation

A new location representing a virtual memory address will be returned here.  If the location cannot be linearized into a virtual memory address (e.g.: the location represents an enregistered value), this method will fail.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory5 interface](nn-dbgmodel-idebughostmemory5.md)