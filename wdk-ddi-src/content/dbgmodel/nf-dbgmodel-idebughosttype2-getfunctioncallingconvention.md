---
UID: NF:dbgmodel.IDebugHostType2.GetFunctionCallingConvention
title: IDebugHostType2::GetFunctionCallingConvention (dbgmodel.h)
description: The GetFunctionCallingConvention method returns the calling convention of the function.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetFunctionCallingConvention"]
ms.keywords: IDebugHostType2::GetFunctionCallingConvention, GetFunctionCallingConvention, IDebugHostType2.GetFunctionCallingConvention, IDebugHostType2::GetFunctionCallingConvention, IDebugHostType2.GetFunctionCallingConvention
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
 - IDebugHostType2::GetFunctionCallingConvention
 - dbgmodel/IDebugHostType2::GetFunctionCallingConvention
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetFunctionCallingConvention
---

# IDebugHostType2::GetFunctionCallingConvention


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

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

