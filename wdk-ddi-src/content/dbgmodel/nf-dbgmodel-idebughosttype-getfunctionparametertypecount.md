---
UID: NF:dbgmodel.IDebugHostType.GetFunctionParameterTypeCount
title: IDebugHostType::GetFunctionParameterTypeCount (dbgmodel.h)
description: The GetFunctionParameterTypeCount method returns the number of arguments that the function takes.
ms.assetid: 394a5b18-fa42-42cd-b92a-200e99f5b6ca
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostType::GetFunctionParameterTypeCount, GetFunctionParameterTypeCount, IDebugHostType.GetFunctionParameterTypeCount, IDebugHostType::GetFunctionParameterTypeCount, IDebugHostType.GetFunctionParameterTypeCount
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostType.GetFunctionParameterTypeCount
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetFunctionParameterTypeCount


## -description

The GetFunctionParameterTypeCount method returns the number of arguments that the function takes. Note that the C/C++ ellipsis based variable argument marker is not considered in this count. The presence of such must be detected via the GetFunctionVarArgsKind method. This will only include arguments before the ellipsis. 

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

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
