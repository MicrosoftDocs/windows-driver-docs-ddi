---
UID: NF:dbgmodel.IDebugHostMemory.ReadBytes
title: IDebugHostMemory::ReadBytes
author: windows-driver-content
description: TBD
ms.assetid: 04a34999-91f0-4d6e-be0d-1babc8bd6459
ms.author: windowsdriverdev
ms.date: 09/18/2018
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


---

# IDebugHostMemory::ReadBytes


## -description

Reads a number of bytes from the address space of the target as defined by the inpassed context and location.
The number of bytes read is returned in "bytesRead" upon success.

## -parameters

### -param context

### -param location

### -param buffer

### -param bufferSize

### -param bytesRead


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)