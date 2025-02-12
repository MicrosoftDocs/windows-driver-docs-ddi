---
UID: NF:dbgmodel.IDebugHostType3.GetFunctionParameterTypeCount
tech.root: debugger
title: IDebugHostType3::GetFunctionParameterTypeCount
ms.date: 01/26/2025
targetos: Windows
description: The GetFunctionParameterTypeCount method, when called on a type for a function, gets the number of arguments that the function takes.
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
 - IDebugHostType3::GetFunctionParameterTypeCount
f1_keywords:
 - IDebugHostType3::GetFunctionParameterTypeCount
 - dbgmodel/IDebugHostType3::GetFunctionParameterTypeCount
dev_langs:
 - c++
helpviewer_keywords:
 - GetFunctionParameterTypeCount
---

## -description

The GetFunctionParameterTypeCount method returns the number of arguments that the function takes. 

Note that the C/C++ ellipsis based variable argument marker is not considered in this count. The presence of such must be detected via the [GetFunctionVarArgsKind method](nf-dbgmodel-idebughosttype3-getfunctionvarargskind.md). This will only include arguments before the ellipsis.

## -parameters

### -param count

The number of arguments to the function (ignoring the variable argument ellipsis) will be returned here. The types of each individual argument may be acquired via the [GetFunctionParameterTypeAt method](nf-dbgmodel-idebughosttype3-getfunctionparametertypeat.md).

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a function (see FindTypeByName) */

ULONG64 count;
if (SUCCEEDED(spType->GetFunctionParameterTypeCount(&count)))
{
    // count is the number of parameters the function takes.  This does not 
    // include any ellipsis for variable arguments.
}
```

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
