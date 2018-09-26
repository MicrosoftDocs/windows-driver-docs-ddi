---
UID: NF:dbgmodel.IDebugHostMemory2.ReadBytes
title: IDebugHostMemory2::ReadBytes
author: windows-driver-content
description: TBD
ms.assetid: db0ae688-692c-468f-aa1b-7dca69a53ee2
ms.author: windowsdriverdev
ms.date: 09/18/2018
ms.topic: method
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostMemory2.ReadBytes
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostMemory2::ReadBytes


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

[IDebugHostMemory2 interface](nn-dbgmodel-idebughostmemory2.md)
