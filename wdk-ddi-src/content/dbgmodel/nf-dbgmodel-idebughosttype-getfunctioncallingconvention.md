---
UID: NF:dbgmodel.IDebugHostType.GetFunctionCallingConvention
title: IDebugHostType::GetFunctionCallingConvention (dbgmodel.h)
description: The GetFunctionCallingConvention method returns the calling convention of the function. Such is returned as a member of the CallingConventionKind enumeration.
ms.date: 09/07/2018
keywords: ["IDebugHostType::GetFunctionCallingConvention"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType::GetFunctionCallingConvention
 - dbgmodel/IDebugHostType::GetFunctionCallingConvention
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType.GetFunctionCallingConvention
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

