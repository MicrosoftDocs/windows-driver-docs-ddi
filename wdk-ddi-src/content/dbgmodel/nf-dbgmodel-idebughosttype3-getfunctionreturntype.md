---
UID: NF:dbgmodel.IDebugHostType3.GetFunctionReturnType
tech.root: debugger
title: IDebugHostType3::GetFunctionReturnType
ms.date: 01/26/2025
targetos: Windows
description: The GetFunctionReturnType method, when called on a type for a function, gets the return type of the function.
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
 - IDebugHostType3::GetFunctionReturnType
f1_keywords:
 - IDebugHostType3::GetFunctionReturnType
 - dbgmodel/IDebugHostType3::GetFunctionReturnType
dev_langs:
 - c++
helpviewer_keywords:
 - GetFunctionReturnType
---

## -description

The GetFunctionReturnType method returns the return type of the function.

## -parameters

### -param returnType

A type symbol indicating the return type of the function is returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a function (see FindTypeByName) */

ComPtr<IDebugHostType> spReturnType;
if (SUCCEEDED(spType->GetFunctionReturnType(&spReturnType)))
{
    // spReturnType is the type symbol for the return type of the function.
}
```

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
