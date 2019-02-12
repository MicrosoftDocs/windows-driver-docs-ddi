---
UID: NF:dbgmodel.IDebugHostSymbol2.GetContainingModule
title: IDebugHostSymbol2::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module. 
ms.assetid: e1519a62-79ac-4a65-9245-b6f21e073556
ms.date: 09/21/2018
ms.topic: method
ms.keywords: IDebugHostSymbol2::GetContainingModule, GetContainingModule, IDebugHostSymbol2.GetContainingModule, IDebugHostSymbol2::GetContainingModule, IDebugHostSymbol2.GetContainingModule
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
-	IDebugHostSymbol2.GetContainingModule
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbol2::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.
    
## -parameters

### -param containingModule
The module which contains the symbol will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)
