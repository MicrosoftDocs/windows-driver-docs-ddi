---
UID: NF:dbgmodel.IDebugHostType2.GetContext
title: IDebugHostType2::GetContext (dbgmodel.h)
description: The GetContext method returns the context where the symbol is valid.
ms.assetid: b40edde3-231c-44fd-8af6-447a3b99dc82
ms.date: 09/20/2018
f1_keywords:
 - "dbgmodel/IDebugHostType2.GetContext"
ms.keywords: IDebugHostType2::GetContext, GetContext, IDebugHostType2.GetContext, IDebugHostType2::GetContext, IDebugHostType2.GetContext
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
- IDebugHostType2.GetContext
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType2::GetContext


## -description

The GetContext method returns the context where the symbol is valid. While this will represent things such as the debug target and process/address space in which the symbol exists, it may not be as specific as a context retrieved from other means (e.g.: from an [IModelObject](nn-dbgmodel-imodelobject.md)). 

## -parameters

### -param context
The host context in which the symbol is located will be returned here.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
