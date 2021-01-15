---
UID: NF:dbgmodel.IDebugHostBaseClass.GetContainingModule
title: IDebugHostBaseClass::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.
ms.date: 09/21/2018
keywords: ["IDebugHostBaseClass::GetContainingModule"]
ms.keywords: IDebugHostBaseClass::GetContainingModule, GetContainingModule, IDebugHostBaseClass.GetContainingModule, IDebugHostBaseClass::GetContainingModule, IDebugHostBaseClass.GetContainingModule
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
 - IDebugHostBaseClass::GetContainingModule
 - dbgmodel/IDebugHostBaseClass::GetContainingModule
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass::GetContainingModule
---

# IDebugHostBaseClass::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.

## -parameters

### -param containingModule

The module which contains the symbol will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostBaseClass interface](nn-dbgmodel-idebughostbaseclass.md)

