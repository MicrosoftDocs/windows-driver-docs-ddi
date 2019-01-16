---
UID: NF:dbgmodel.IDebugHostSymbol2.GetType
title: IDebugHostSymbol2::GetType
description: Returns the type (e.g. "int *") of the symbol if the symbol has a type.
ms.assetid: 145f338d-07e2-49ee-ba1b-dfe1f9fd1237
ms.date: 09/21/2018
ms.topic: method
ms.keywords: IDebugHostSymbol2::GetType, GetType, IDebugHostSymbol2.GetType, IDebugHostSymbol2::GetType, IDebugHostSymbol2.GetType
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
-	IDebugHostSymbol2.GetType
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbol2::GetType


## -description
Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.


## -remarks

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)
