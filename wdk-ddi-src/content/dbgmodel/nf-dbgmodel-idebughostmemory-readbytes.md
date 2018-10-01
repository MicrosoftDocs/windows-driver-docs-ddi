---
UID: NF:dbgmodel.IDebugHostMemory.ReadBytes
title: IDebugHostMemory::ReadBytes
author: windows-driver-content
description: TBD
ms.assetid: 04a34999-91f0-4d6e-be0d-1babc8bd6459
ms.author: windowsdriverdev
ms.date: 09/28/2018
ms.topic: method
ms.keywords: IDebugHostMemory::ReadBytes, ReadBytes, IDebugHostMemory.ReadBytes, IDebugHostMemory::ReadBytes, IDebugHostMemory.ReadBytes
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
-	IDebugHostMemory.ReadBytes
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostMemory::ReadBytes


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

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)
