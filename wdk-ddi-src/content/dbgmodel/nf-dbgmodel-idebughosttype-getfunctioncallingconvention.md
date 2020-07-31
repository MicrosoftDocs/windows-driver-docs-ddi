---
UID: NF:dbgmodel.IDebugHostType.GetFunctionCallingConvention
title: IDebugHostType::GetFunctionCallingConvention (dbgmodel.h)
description: The GetFunctionCallingConvention method returns the calling convention of the function. Such is returned as a member of the CallingConventionKind enumeration. 
ms.assetid: 7c0b15e9-abd8-4b17-abc8-2212205875fa
ms.date: 09/07/2018
keywords: ["IDebugHostType::GetFunctionCallingConvention"]
f1_keywords:
 - "dbgmodel/IDebugHostType.GetFunctionCallingConvention"
 - "IDebugHostType.GetFunctionCallingConvention"
ms.keywords: IDebugHostType::GetFunctionCallingConvention, GetFunctionCallingConvention, IDebugHostType.GetFunctionCallingConvention, IDebugHostType::GetFunctionCallingConvention, IDebugHostType.GetFunctionCallingConvention
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
- IDebugHostType.GetFunctionCallingConvention
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetFunctionCallingConvention


## -description

The GetFunctionCallingConvention method returns the calling convention of the function. Such is returned as a member of the CallingConventionKind enumeration. 

## -parameters

### -param conventionKind
The calling convention of the function is returned here as a member of the CallingConventionKind enumeration.



## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule> spType; /* get a type for some function type (see FindTypeByName) */

CallingConventionKind conv;
if (SUCCEEDED(spType->GetCallingConvention(&conv)))
{
    // conv indicates the calling convention (e.g.: cdecl, thiscall, etc...)
}
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
