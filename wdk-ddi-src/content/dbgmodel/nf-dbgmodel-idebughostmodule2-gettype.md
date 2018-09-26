---
UID: NF:dbgmodel.IDebugHostModule2.GetType
title: IDebugHostModule2::GetType
author: windows-driver-content
description: TBD
ms.assetid: 87eb7c87-71e0-4d69-84e7-12d5b28bc2dc
ms.author: windowsdriverdev
ms.date: 09/21/2018 
ms.topic: method
ms.keywords: IDebugHostModule2::GetType, GetType, IDebugHostModule2.GetType, IDebugHostModule2::GetType, IDebugHostModule2.GetType
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
-	IDebugHostModule2.GetType
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostModule2::GetType


## -description

Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
