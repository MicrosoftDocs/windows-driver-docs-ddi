---
UID: NF:dbgmodel.IDebugHostType2.GetContainingModule
title: IDebugHostType2::GetContainingModule (dbgmodel.h)
description: "The IDebugHostType2::GetContainingModule method, when called on a symbol, gets the module that contains the symbol if the symbol has a containing module."
ms.date: 09/21/2018
keywords: ["IDebugHostType2::GetContainingModule"]
ms.keywords: IDebugHostType2::GetContainingModule, GetContainingModule, IDebugHostType2.GetContainingModule, IDebugHostType2::GetContainingModule, IDebugHostType2.GetContainingModule
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
 - IDebugHostType2::GetContainingModule
 - dbgmodel/IDebugHostType2::GetContainingModule
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetContainingModule
---

# IDebugHostType2::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.

## -parameters

### -param containingModule

The module which contains the symbol will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

