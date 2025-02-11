---
UID: NF:dbgmodel.IDebugHostType3.GetFunctionCallingConvention
tech.root: debugger
title: IDebugHostType3::GetFunctionCallingConvention
ms.date: 01/26/2025
targetos: Windows
description: The GetFunctionCallingConvention method returns the calling convention of a function type.
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
 - IDebugHostType3::GetFunctionCallingConvention
f1_keywords:
 - IDebugHostType3::GetFunctionCallingConvention
 - dbgmodel/IDebugHostType3::GetFunctionCallingConvention
dev_langs:
 - c++
helpviewer_keywords:
 - GetFunctionCallingConvention
---

## -description

The GetFunctionCallingConvention method returns the calling convention of the function. Such is returned as a member of the [CallingConventionKind enumeration](ne-dbgmodel-callingconventionkind).

## -parameters

### -param conventionKind

The calling convention of the function is returned here as a member of the [CallingConventionKind enumeration](ne-dbgmodel-callingconventionkind).

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
