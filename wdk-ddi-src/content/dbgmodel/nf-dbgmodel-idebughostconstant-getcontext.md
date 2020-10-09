---
UID: NF:dbgmodel.IDebugHostConstant.GetContext
title: IDebugHostConstant::GetContext (dbgmodel.h)
description: The GetContext method returns the context where the symbol is valid.
ms.assetid: 97791b67-24ec-45e3-aa45-2c4eacd5ec89
ms.date: 09/10/2018
keywords: ["IDebugHostConstant::GetContext"]
ms.keywords: IDebugHostConstant::GetContext, GetContext, IDebugHostConstant.GetContext, IDebugHostConstant::GetContext, IDebugHostConstant.GetContext
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
 - IDebugHostConstant::GetContext
 - dbgmodel/IDebugHostConstant::GetContext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostConstant.GetContext
---

# IDebugHostConstant::GetContext


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

[IDebugHostConstant interface](nn-dbgmodel-idebughostconstant.md)

