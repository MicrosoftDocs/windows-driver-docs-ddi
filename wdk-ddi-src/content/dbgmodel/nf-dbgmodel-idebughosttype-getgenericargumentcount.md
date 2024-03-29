---
UID: NF:dbgmodel.IDebugHostType.GetGenericArgumentCount
title: IDebugHostType::GetGenericArgumentCount (dbgmodel.h)
description: "The IDebugHostType::GetGenericArgumentCount method, when called on a type, gets the number of generic arguments to the type."
ms.date: 09/11/2018
keywords: ["IDebugHostType::GetGenericArgumentCount"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType::GetGenericArgumentCount
 - dbgmodel/IDebugHostType::GetGenericArgumentCount
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType::GetGenericArgumentCount
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

