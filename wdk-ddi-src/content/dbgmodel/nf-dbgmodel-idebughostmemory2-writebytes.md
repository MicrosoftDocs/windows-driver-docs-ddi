---
UID: NF:dbgmodel.IDebugHostMemory2.WriteBytes
title: IDebugHostMemory2::WriteBytes
author: windows-driver-content
description: TBD
ms.assetid: 63704020-5225-47dd-a388-151b5b02885f
ms.author: windowsdriverdev
ms.date: 09/18/2018
ms.topic: method
ms.keywords: IDebugHostMemory2::WriteBytes, WriteBytes, IDebugHostMemory2.WriteBytes, IDebugHostMemory2::WriteBytes, IDebugHostMemory2.WriteBytes
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
-	IDebugHostMemory2.WriteBytes
product: Windows
targetos: Windows


---

# IDebugHostMemory2::WriteBytes


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
This method returns HRESULT.
## -remarks

## -see-also