---
UID: NF:dbgmodel.IDebugHostMemory5.WritePointers
tech.root: debugger
title: IDebugHostMemory5::WritePointers
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostMemory5::WritePointers method writes a number of pointers into the address space of the target.
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
 - IDebugHostMemory5::WritePointers
f1_keywords:
 - IDebugHostMemory5::WritePointers
 - dbgmodel/IDebugHostMemory5::WritePointers
dev_langs:
 - c++
helpviewer_keywords:
 - WritePointers
---

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

[IDebugHostMemory5 interface](nn-dbgmodel-idebughostmemory5.md)