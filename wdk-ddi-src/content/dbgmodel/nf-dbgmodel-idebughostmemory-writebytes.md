---
UID: NF:dbgmodel.IDebugHostMemory.WriteBytes
title: IDebugHostMemory::WriteBytes (dbgmodel.h)
description: "The IDebugHostMemory::WriteBytes method writes a number of bytes to the address space of the target for a given context and location."
ms.date: 09/28/2018
keywords: ["IDebugHostMemory::WriteBytes"]
ms.keywords: IDebugHostMemory::WriteBytes, WriteBytes, IDebugHostMemory.WriteBytes, IDebugHostMemory::WriteBytes, IDebugHostMemory.WriteBytes
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostMemory::WriteBytes
 - dbgmodel/IDebugHostMemory::WriteBytes
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostMemory::WriteBytes
---

# IDebugHostMemory::WriteBytes


## -description

 Writes a number of bytes to the address space of the target as defined by the inpassed context and location.

 The number of bytes written is returned in "bytesWritten" upon success.

## -parameters

### -param context

The host context in which to write bytes.  This represents, for example, the address space in which the location exists.

### -param location

The location at which to write bytes.  This location may represent a virtual address within the address space defined by context or it may represent something like a register within a context record for a thread.

### -param buffer

The bytes to write to the debug target.

### -param bufferSize

The size of the buffer / number of bytes to write to the debug target.

### -param bytesWritten

The number of bytes actually written to the debug target will be returned here.  If the method can complete a partial write, S_FALSE will be returned and the value in bytesWritten may be less than the requested number of bytes.  If the method returns S_OK, a full write was completed.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)

