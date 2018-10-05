---
UID: NF:dbgmodel.IDebugHostModule.GetType
title: IDebugHostModule::GetType
author: windows-driver-content
description: Returns the type (e.g. "int *") of the symbol if the symbol has a type. 
ms.assetid: 8300bd87-8264-47ef-9273-c70296063656
ms.author: windowsdriverdev
ms.date: 09/21/2018 
ms.topic: method
ms.keywords: IDebugHostModule::GetType, GetType, IDebugHostModule.GetType, IDebugHostModule::GetType, IDebugHostModule.GetType
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
-	IDebugHostModule.GetType
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostModule::GetType


## -description


Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.


## -remarks

## -see-also

[IDebugHostModule interface](nn-dbgmodel-idebughostmodule.md)
