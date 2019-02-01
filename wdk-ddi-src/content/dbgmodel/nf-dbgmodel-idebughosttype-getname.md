---
UID: NF:dbgmodel.IDebugHostType.GetName
title: IDebugHostType::GetName (dbgmodel.h)
description: Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.
ms.assetid: ec08f1c6-c70b-4007-b4a3-b5a1099edc76
ms.date: 09/21/2018
ms.topic: method
ms.keywords: IDebugHostType::GetName, GetName, IDebugHostType.GetName, IDebugHostType::GetName, IDebugHostType.GetName
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
-	IDebugHostType.GetName
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.


## -parameters

### -param symbolName
The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns
This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
