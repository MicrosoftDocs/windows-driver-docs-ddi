---
UID: NF:dbgmodel.IDebugHostModule3.GetContext
tech.root: debugger
title: IDebugHostModule3::GetContext
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule3::GetContext method, when called on a symbol, gets the host context in which the symbol is located.
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
 - IDebugHostModule3::GetContext
f1_keywords:
 - IDebugHostModule3::GetContext
 - dbgmodel/IDebugHostModule3::GetContext
dev_langs:
 - c++
helpviewer_keywords:
 - GetContext
---

## -description

The GetContext method returns the context where the symbol is valid. While this will represent things such as the debug target and process/address space in which the symbol exists, it may not be as specific as a context retrieved from other means (e.g.: from an [IModelObject](nn-dbgmodel-imodelobject.md)).

## -parameters

### -param context

The host context in which the symbol is located will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHostSymbol> spSymbol; /* get a symbol */

ComPtr<IDebugHostContext> spContext;
if (SUCCEEDED(spSymbol->GetContext(&spContext)))
{
    // spContext will contain the context that the symbol is within 
    // (e.g.: session, process)
}
```

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)