---
UID: NF:dbgmodel.IDebugHostType.GetArrayDimensions
title: IDebugHostType::GetArrayDimensions (dbgmodel.h)
description: The GetArrayDimensions method returns a set of descriptors, one for each dimension of the array as indicated by the GetArrayDimensionality method.
ms.assetid: a5950b75-3dea-4076-bcff-71d530899c98
ms.date: 09/07/2018
keywords: ["IDebugHostType::GetArrayDimensions"]
ms.keywords: IDebugHostType::GetArrayDimensions, GetArrayDimensions, IDebugHostType.GetArrayDimensions, IDebugHostType::GetArrayDimensions, IDebugHostType.GetArrayDimensions
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType::GetArrayDimensions
 - dbgmodel/IDebugHostType::GetArrayDimensions
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType.GetArrayDimensions
---

# IDebugHostType::GetArrayDimensions


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

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for some array (see FindTypeByName) */

ArrayDimension adim;
if (SUCCEEDED(spType->GetArrayDimensions(1, &adim)))
{
    // adim indicates information about the dimension.  For C/C++, length is 
    // the largely relevant field.  C/C++ arrays are always zero based.  The 
    // stride field would indicate the size of the array element type.
}
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

