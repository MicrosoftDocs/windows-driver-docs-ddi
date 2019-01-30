---
UID: NS:dbgmodel.ArrayDimension
title: ArrayDimension (dbgmodel.h)
description: Defines the memory layout of one dimension of an array.
ms.assetid: e99b1f99-d853-4159-9656-1a6b83f43ac1
ms.date: 07/16/2018
ms.topic: struct
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
tech.root: debugger
ms.custom: RS5
---

# ArrayDimension structure

## -description

Defines the memory layout of one dimension of an array.


## -struct-fields

### -field LowerBound
The lower bounds of the array.  For C style zero based arrays, this will always be zero.  There is no uniform restriction that all arrays represented by these interfaces are zero based.
 
### -field Length
Defines the length of the dimension.  The dimension is considered to be of the form [LowerBound, LowerBound + Length)

### -field Stride
Defines how many bytes to move forward in memory to walk from index N of the dimension to index N + 1

## -remarks

For C-style arrays, a single array dimension is returned here with values which are always: 
LowerBound = 0

Length = ARRAYSIZE(array)

Stride = sizeof(elementType)

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
