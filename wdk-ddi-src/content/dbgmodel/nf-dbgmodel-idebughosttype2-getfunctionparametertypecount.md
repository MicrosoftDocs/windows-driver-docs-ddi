---
UID: NF:dbgmodel.IDebugHostType2.GetFunctionParameterTypeCount
title: IDebugHostType2::GetFunctionParameterTypeCount (dbgmodel.h)
description: "The IDebugHostType2::GetFunctionParameterTypeCount method, when called on a type for a function, gets the number of arguments that the function takes."
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetFunctionParameterTypeCount"]
ms.keywords: IDebugHostType2::GetFunctionParameterTypeCount, GetFunctionParameterTypeCount, IDebugHostType2.GetFunctionParameterTypeCount, IDebugHostType2::GetFunctionParameterTypeCount, IDebugHostType2.GetFunctionParameterTypeCount
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
 - IDebugHostType2::GetFunctionParameterTypeCount
 - dbgmodel/IDebugHostType2::GetFunctionParameterTypeCount
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetFunctionParameterTypeCount
---

# IDebugHostType2::GetFunctionParameterTypeCount


## -description

The GetFunctionParameterTypeCount method returns the number of arguments that the function takes. 

Note that the C/C++ ellipsis based variable argument marker is not considered in this count. The presence of such must be detected via the GetFunctionVarArgsKind method. This will only include arguments before the ellipsis.

## -parameters

### -param count

The number of arguments to the function (ignoring the variable argument ellipsis) will be returned here. The types of each individual argument may be acquired via the GetFunctionParameterTypeAt method.

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

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

