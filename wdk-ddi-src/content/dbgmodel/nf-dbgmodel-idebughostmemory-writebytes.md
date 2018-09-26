---
UID: NF:dbgmodel.IDebugHostMemory.WriteBytes
title: IDebugHostMemory::WriteBytes
author: windows-driver-content
description: TBD
ms.assetid: dc230851-0655-418f-8cba-0e9bc4f885a5
ms.author: windowsdriverdev
ms.date: 09/18/2018 
ms.topic: method
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
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostMemory.WriteBytes
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostMemory::WriteBytes


## -description

 Writes a number of bytes to the address space of the target as defined by the inpassed context and location.

 The number of bytes written is returned in "bytesWritten" upon success.

## -parameters

### -param context

### -param location

### -param buffer

### -param bufferSize

### -param bytesWritten


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)
