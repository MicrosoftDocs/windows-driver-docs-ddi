---
UID: NF:dbgmodel.IDebugHostData.GetContainingModule
title: IDebugHostData::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.
ms.assetid: f4dc58a1-ef47-45ff-b142-a9e9279f5ab5
ms.date: 09/10/2018
keywords: ["IDebugHostData::GetContainingModule"]
f1_keywords:
 - "dbgmodel/IDebugHostData.GetContainingModule"
 - "IDebugHostData.GetContainingModule"
ms.keywords: IDebugHostData::GetContainingModule, GetContainingModule, IDebugHostData.GetContainingModule, IDebugHostData::GetContainingModule, IDebugHostData.GetContainingModule
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
- IDebugHostData.GetContainingModule
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostData::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.

## -parameters

### -param containingModule
The module which contains the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.
## -remarks

## -see-also
[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)
