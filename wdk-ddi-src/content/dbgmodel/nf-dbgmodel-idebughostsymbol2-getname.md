---
UID: NF:dbgmodel.IDebugHostSymbol2.GetName
title: IDebugHostSymbol2::GetName
author: windows-driver-content
description: TBD
ms.assetid: 5d6cc64e-d661-4168-9ee7-8f5109435335
ms.author: windowsdriverdev
ms.date: 09/21/2018
ms.topic: method
ms.keywords: IDebugHostSymbol2::GetName, GetName, IDebugHostSymbol2.GetName, IDebugHostSymbol2::GetName, IDebugHostSymbol2.GetName
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
-	IDebugHostSymbol2.GetName
product: Windows
targetos: Windows


---

# IDebugHostSymbol2::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.


## -parameters

### -param symbolName
The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns
This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)