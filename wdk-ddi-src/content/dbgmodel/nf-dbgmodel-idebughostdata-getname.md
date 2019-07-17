---
UID: NF:dbgmodel.IDebugHostData.GetName
title: IDebugHostData::GetName (dbgmodel.h)
description: The GetLocationKind method returns what kind of location the symbol is at according to the LocationKind enumeration. 
ms.assetid: 377c4d13-7349-43ce-8ab8-b2dc84bbf6ea
ms.date: 09/10/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostData.GetName"
ms.keywords: IDebugHostData::GetName, GetName, IDebugHostData.GetName, IDebugHostData::GetName, IDebugHostData.GetName
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
- IDebugHostData.GetName
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostData::GetName


## -description
Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.


## -parameters

### -param symbolName
The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also
[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)
