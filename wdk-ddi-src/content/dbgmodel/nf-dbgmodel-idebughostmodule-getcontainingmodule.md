---
UID: NF:dbgmodel.IDebugHostModule.GetContainingModule
title: IDebugHostModule::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.
ms.assetid: 125fd543-0f5c-4628-8d81-1a4c7689df2c
ms.date: 09/18/2018
ms.topic: method
ms.keywords: IDebugHostModule::GetContainingModule, GetContainingModule, IDebugHostModule.GetContainingModule, IDebugHostModule::GetContainingModule, IDebugHostModule.GetContainingModule
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostModule.GetContainingModule
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule::GetContainingModule


## -description
Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.
    
## -parameters

### -param containingModule
The module which contains the symbol will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDebugHostModule interface](nn-dbgmodel-idebughostmodule.md)
