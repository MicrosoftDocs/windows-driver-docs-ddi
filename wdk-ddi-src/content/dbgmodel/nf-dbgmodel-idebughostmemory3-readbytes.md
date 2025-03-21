---
UID: NF:dbgmodel.IDebugHostMemory3.ReadBytes
tech.root: debugger
title: IDebugHostMemory3::ReadBytes
ms.date: 02/24/2025
targetos: Windows
description: The ReadBytes method reads a number of bytes from the address space of the target for a given context and location.
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
 - IDebugHostMemory3::ReadBytes
f1_keywords:
 - IDebugHostMemory3::ReadBytes
 - dbgmodel/IDebugHostMemory3::ReadBytes
dev_langs:
 - c++
helpviewer_keywords:
 - ReadBytes
---

## -description

Reads a number of bytes from the address space of the target as defined by the inpassed context and location.
The number of bytes read is returned in "bytesRead" upon success.

## -parameters

### -param context

The host context in which to read bytes.  This represents, for example, the address space in which the location exists.

### -param location

The location at which to read bytes.  This location may represent a virtual address within the address space defined by context or it may represent something like a register within a context record for a thread.

### -param buffer

The bytes read from the debug target will be written to this buffer.

### -param bufferSize

The size of the buffer and the number of bytes to read.

### -param bytesRead

The number of bytes actually read from the debug target will be returned here.  If the method can complete a partial read, S_FALSE will be returned and the value in bytesRead may be less than the requested number of bytes.  If the method returns S_OK, a full read was completed.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory3 interface](nn-dbgmodel-idebughostmemory3.md)