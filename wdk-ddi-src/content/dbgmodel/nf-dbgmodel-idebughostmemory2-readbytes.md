---
UID: NF:dbgmodel.IDebugHostMemory2.ReadBytes
title: IDebugHostMemory2::ReadBytes (dbgmodel.h)
description: Reads a number of bytes from the address space of the target as defined by the inpassed context and location.
ms.assetid: db0ae688-692c-468f-aa1b-7dca69a53ee2
ms.date: 09/28/2018
keywords: ["IDebugHostMemory2::ReadBytes"]
f1_keywords:
 - "dbgmodel/IDebugHostMemory2.ReadBytes"
 - "IDebugHostMemory2.ReadBytes"
ms.keywords: IDebugHostMemory2::ReadBytes, ReadBytes, IDebugHostMemory2.ReadBytes, IDebugHostMemory2::ReadBytes, IDebugHostMemory2.ReadBytes
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostMemory2.ReadBytes
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostMemory2::ReadBytes


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

[IDebugHostMemory2 interface](nn-dbgmodel-idebughostmemory2.md)
