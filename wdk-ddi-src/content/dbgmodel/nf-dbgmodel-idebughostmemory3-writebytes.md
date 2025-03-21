---
UID: NF:dbgmodel.IDebugHostMemory3.WriteBytes
tech.root: debugger
title: IDebugHostMemory3::WriteBytes
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostMemory3::WriteBytes method writes a number of bytes to the address space of the target for a given context and location.
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
 - IDebugHostMemory3::WriteBytes
f1_keywords:
 - IDebugHostMemory3::WriteBytes
 - dbgmodel/IDebugHostMemory3::WriteBytes
dev_langs:
 - c++
helpviewer_keywords:
 - WriteBytes
---

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

This method returns HRESULT.

## -remarks

## -see-also

[IDebugHostMemory3 interface](nn-dbgmodel-idebughostmemory3.md)