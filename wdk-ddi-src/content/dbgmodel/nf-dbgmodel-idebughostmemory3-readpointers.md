---
UID: NF:dbgmodel.IDebugHostMemory3.ReadPointers
tech.root: debugger
title: IDebugHostMemory3::ReadPointers
ms.date: 02/24/2025
targetos: Windows
description: The ReadPointers method reads a number of pointers from the address space of the target for a given context and location.
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
 - IDebugHostMemory3::ReadPointers
f1_keywords:
 - IDebugHostMemory3::ReadPointers
 - dbgmodel/IDebugHostMemory3::ReadPointers
dev_langs:
 - c++
helpviewer_keywords:
 - ReadPointers
---

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

[IDebugHostMemory3 interface](nn-dbgmodel-idebughostmemory3.md)