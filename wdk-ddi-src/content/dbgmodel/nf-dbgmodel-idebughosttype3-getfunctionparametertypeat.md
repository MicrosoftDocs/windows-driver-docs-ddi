---
UID: NF:dbgmodel.IDebugHostType3.GetFunctionParameterTypeAt
tech.root: debugger
title: IDebugHostType3::GetFunctionParameterTypeAt
ms.date: 01/26/2025
targetos: Windows
description: The GetFunctionParameterTypeAt method, when called on a function type, gets the parameter type at a given index in the function's argument list.
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
 - IDebugHostType3::GetFunctionParameterTypeAt
f1_keywords:
 - IDebugHostType3::GetFunctionParameterTypeAt
 - dbgmodel/IDebugHostType3::GetFunctionParameterTypeAt
dev_langs:
 - c++
helpviewer_keywords:
 - GetFunctionParameterTypeAt
---

## -description

The GetFunctionParameterTypeAt method returns the type of the i-th argument to the function.

## -parameters

### -param i

A zero based index into the function argument list for which to retrieve the argument type.

### -param parameterType

The type of the i-th argument to the function will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a function (see FindTypeByName) */

// enumerate (in order) the types of parameters the function takes
ULONG64 count;
if (SUCCEEDED(spType->GetFunctionParameterTypeCount(&count)))
{
    for (ULONG64 i = 0; i < count; ++i)
    {
        ComPtr<IDebugHostType> spParamType;
        if (SUCCEEDED(spType->GetFunctionParameterTypeAt(i, &spParamType)))
        {
            // spParamType is the type symbol for the type of parameter the 
            // function takes at position i in the argument list.
        }
    }
}
```

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)

