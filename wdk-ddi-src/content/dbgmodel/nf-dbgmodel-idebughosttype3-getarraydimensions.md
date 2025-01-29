---
UID: NF:dbgmodel.IDebugHostType3.GetArrayDimensions
tech.root: debugger
title: IDebugHostType3::GetArrayDimensions
ms.date: 01/26/2025
targetos: Windows
description: The GetArrayDimensions method, when called on a type for an array, gets a set of descriptors, one for each dimension of the array.
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
 - IDebugHostType3::GetArrayDimensions
f1_keywords:
 - IDebugHostType3::GetArrayDimensions
 - dbgmodel/IDebugHostType3::GetArrayDimensions
dev_langs:
 - c++
helpviewer_keywords:
 - GetArrayDimensions
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
