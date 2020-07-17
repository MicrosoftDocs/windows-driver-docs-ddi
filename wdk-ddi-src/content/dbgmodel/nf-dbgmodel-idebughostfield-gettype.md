---
UID: NF:dbgmodel.IDebugHostField.GetType
title: IDebugHostField::GetType (dbgmodel.h)
description: Returns the type (e.g. "int *") of the symbol if the symbol has a type.
ms.assetid: db92380d-d0a4-4530-af78-5fe60a35861b
ms.date: 09/21/2018
keywords: ["IDebugHostField::GetType"]
f1_keywords:
 - "dbgmodel/IDebugHostField.GetType"
 - "IDebugHostField.GetType"
ms.keywords: IDebugHostField::GetType, GetType, IDebugHostField.GetType, IDebugHostField::GetType, IDebugHostField.GetType
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
- IDebugHostField.GetType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostField::GetType


## -description

Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)
