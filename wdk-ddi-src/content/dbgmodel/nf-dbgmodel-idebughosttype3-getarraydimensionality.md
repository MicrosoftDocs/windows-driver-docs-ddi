---
UID: NF:dbgmodel.IDebugHostType3.GetArrayDimensionality
tech.root: debugger
title: IDebugHostType3::GetArrayDimensionality
ms.date: 01/26/2025
targetos: Windows
description: The GetArrayDimensionality method returns the number of dimensions in an array type.
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
 - IDebugHostType3::GetArrayDimensionality
f1_keywords:
 - IDebugHostType3::GetArrayDimensionality
 - dbgmodel/IDebugHostType3::GetArrayDimensionality
dev_langs:
 - c++
helpviewer_keywords:
 - GetArrayDimensionality
---

## -description

The GetArrayDimensionality method returns the number of dimensions that the array is indexed in. For C style arrays, the value returned here will always be 1.

## -parameters

### -param arrayDimensionality

The number of dimensions that the array is indexed in will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for some array (see FindTypeByName) */

ULONG64 arrayDims;
if (SUCCEEDED(spType->GetArrayDimensionality(&arrayDims)))
{
    // arrayDims is the dimensionality of the array.  For C/C++, this is always 1.
}
```

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
