---
UID: NF:dbgmodel.IDebugHostField.GetContainingModule
title: IDebugHostField::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.
ms.assetid: c57c3e8d-1054-4928-aa35-01febde6218e
ms.date: 09/12/2018
keywords: ["IDebugHostField::GetContainingModule"]
ms.keywords: IDebugHostField::GetContainingModule, GetContainingModule, IDebugHostField.GetContainingModule, IDebugHostField::GetContainingModule, IDebugHostField.GetContainingModule
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
 - IDebugHostField::GetContainingModule
 - dbgmodel/IDebugHostField::GetContainingModule
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostField.GetContainingModule
---

# IDebugHostField::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.

## -parameters

### -param containingModule

The module which contains the symbol will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)

