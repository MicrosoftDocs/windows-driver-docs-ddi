---
UID: NF:dbgmodel.IDebugHostBaseClass.GetContainingModule
title: IDebugHostBaseClass::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.
ms.assetid: 40159a9f-c3f1-4519-86a8-9ec22909e359
ms.date: 09/21/2018
keywords: ["IDebugHostBaseClass::GetContainingModule"]
f1_keywords:
 - "dbgmodel/IDebugHostBaseClass.GetContainingModule"
 - "IDebugHostBaseClass.GetContainingModule"
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostBaseClass.GetContainingModule
targetos: Windows
tech.root: debugger
ms.custom: RS5
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
