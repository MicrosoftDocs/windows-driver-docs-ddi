---
UID: NF:dbgmodel.IDebugHostType2.GetArrayDimensionality
title: IDebugHostType2::GetArrayDimensionality
author: windows-driver-content
description: TBD
ms.assetid: b2a2dfe1-733b-4349-b99b-11856ae10d35
ms.author: windowsdriverdev
ms.date: 09/20/2018 
ms.topic: method
ms.keywords: IDebugHostType2::GetArrayDimensionality, GetArrayDimensionality, IDebugHostType2.GetArrayDimensionality, IDebugHostType2::GetArrayDimensionality, IDebugHostType2.GetArrayDimensionality
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
-	IDebugHostType2.GetArrayDimensionality
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostType2::GetArrayDimensionality


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
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
