---
UID: NF:dbgmodel.IDebugHostType.GetContext
title: IDebugHostType::GetContext (dbgmodel.h)
description: "The IDebugHostType::GetContext method, when called on a symbol, gets the host context in which the symbol is located."
ms.date: 08/22/2018
keywords: ["IDebugHostType::GetContext"]
ms.keywords: IDebugHostType::GetContext, GetContext, IDebugHostType.GetContext, IDebugHostType::GetContext, IDebugHostType.GetContext
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
 - IDebugHostType::GetContext
 - dbgmodel/IDebugHostType::GetContext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType::GetContext
---

# IDebugHostType::GetContext


## -description

The GetContext method returns the context where the symbol is valid. While this will represent things such as the debug target and process/address space in which the symbol exists, it may not be as specific as a context retrieved from other means (e.g.: from an [IModelObject](nn-dbgmodel-imodelobject.md)).

## -parameters

### -param context

The host context in which the symbol is located will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

