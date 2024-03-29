---
UID: NF:dbgmodel.IDebugHostType.GetFunctionReturnType
title: IDebugHostType::GetFunctionReturnType (dbgmodel.h)
description: "The IDebugHostType::GetFunctionReturnType method, when called on a type for a function, gets the return type of the function."
ms.date: 08/22/2018
keywords: ["IDebugHostType::GetFunctionReturnType"]
ms.keywords: IDebugHostType::GetFunctionReturnType, GetFunctionReturnType, IDebugHostType.GetFunctionReturnType, IDebugHostType::GetFunctionReturnType, IDebugHostType.GetFunctionReturnType
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
 - IDebugHostType::GetFunctionReturnType
 - dbgmodel/IDebugHostType::GetFunctionReturnType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType::GetFunctionReturnType
---

# IDebugHostType::GetFunctionReturnType


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

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

