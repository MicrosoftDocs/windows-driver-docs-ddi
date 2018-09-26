---
UID: NF:dbgmodel.IDebugHostModule2.GetContainingModule
title: IDebugHostModule2::GetContainingModule
author: windows-driver-content
description: TBD
ms.assetid: 8fe7048a-b09d-49fa-ae9b-8f9e20dcc05f
ms.author: windowsdriverdev
ms.date: 09/21/2018  
ms.topic: method
ms.keywords: IDebugHostModule2::GetContainingModule, GetContainingModule, IDebugHostModule2.GetContainingModule, IDebugHostModule2::GetContainingModule, IDebugHostModule2.GetContainingModule
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
-	IDebugHostModule2.GetContainingModule
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostModule2::GetContainingModule


## -description
Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.
    
## -parameters

### -param containingModule
The module which contains the symbol will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
