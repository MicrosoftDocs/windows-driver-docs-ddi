---
UID: NF:dbgmodel.IDebugHostType.GetGenericArgumentCount
title: IDebugHostType::GetGenericArgumentCount (dbgmodel.h)
description: Returns the number of arguments to the generic/template.
ms.assetid: 1451041e-41f1-47d2-a259-dbdfb46cf8b8
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDebugHostType::GetGenericArgumentCount, GetGenericArgumentCount, IDebugHostType.GetGenericArgumentCount, IDebugHostType::GetGenericArgumentCount, IDebugHostType.GetGenericArgumentCount
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
- IDebugHostType.GetGenericArgumentCount
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetGenericArgumentCount


## -description

Returns the number of arguments to the generic/template.  The returned value must be greater than zero.

## -parameters

### -param argCount
The number of generic arguments (e.g.: template arguments) to the type will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
