---
UID: NF:dbgmodel.IDebugHostData.GetType
title: IDebugHostData::GetType (dbgmodel.h)
description: Returns the type (that is "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
ms.assetid: 765578af-617a-4647-a3bc-b71ec4ffb17b
ms.date: 09/12/2018
f1_keywords:
 - "dbgmodel/IDebugHostData.GetType"
ms.keywords: IDebugHostData::GetType, GetType, IDebugHostData.GetType, IDebugHostData::GetType, IDebugHostData.GetType
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
- IDebugHostData.GetType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostData::GetType


## -description

Returns the type (that is "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also
[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)
