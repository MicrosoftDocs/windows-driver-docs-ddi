---
UID: NS:dbgmodel.ArrayDimension
title: ArrayDimension
author: windows-driver-content
description: 
ms.assetid: e99b1f99-d853-4159-9656-1a6b83f43ac1
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: ArrayDimension, , 
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	ArrayDimension
product: Windows
targetos: Windows
---

# ArrayDimension structure

## -description


## -struct-fields

### -field LowerBound
 
### -field Length
 
### -field Stride
 

## -remarks

For C-style arrays, a single array dimension is returned here with values which are always: 
LowerBound = 0

Length = ARRAYSIZE(array)

Stride = sizeof(elementType)

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
