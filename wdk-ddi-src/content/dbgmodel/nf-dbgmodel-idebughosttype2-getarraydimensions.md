---
UID: NF:dbgmodel.IDebugHostType2.GetArrayDimensions
title: IDebugHostType2::GetArrayDimensions
author: windows-driver-content
description: The GetArrayDimensions method returns a set of descriptors, one for each dimension of the array as indicated by the GetArrayDimensionality method.
ms.assetid: 9d8a0a77-4599-4a86-acb5-6f5bd9563fa4
ms.date: 09/20/2018 
ms.topic: method
ms.keywords: IDebugHostType2::GetArrayDimensions, GetArrayDimensions, IDebugHostType2.GetArrayDimensions, IDebugHostType2::GetArrayDimensions, IDebugHostType2.GetArrayDimensions
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
-	IDebugHostType2.GetArrayDimensions
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostType2::GetArrayDimensions


## -description
The GetArrayDimensions method returns a set of descriptors, one for each dimension of the array as indicated by the GetArrayDimensionality method. Each descriptor is an ArrayDimension structure which describes the starting index, length, and forward stride of each array dimension. This allows descriptions of significantly more powerful array constructs than are allowed in the C type system.

For C-style arrays, a single array dimension is returned here with values which are always: 

- LowerBound = 0
- Length = ARRAYSIZE(array)
- Stride = sizeof(elementType)


## -parameters

### -param dimensions
Indicates the number of dimension descriptors to fetch. This must be the value acquired from a call to GetArrayDimensionality.
A buffer of dimensions ArrayDimension structures which will be filled in to fully describe the layout of the array in memory.

### -param pDimensions
A buffer of dimensions ArrayDimension structures which will be filled in to fully describe the layout of the array in memory.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
