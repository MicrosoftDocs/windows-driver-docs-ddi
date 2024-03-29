---
UID: NF:dbgmodel.IDebugHostType.GetType
title: IDebugHostType::GetType (dbgmodel.h)
description: "The IDebugHostType::GetType method, when called on a symbol, gets the type of symbol, such as int *."
ms.date: 09/10/2018
keywords: ["IDebugHostType::GetType"]
ms.keywords: IDebugHostType::GetType, GetType, IDebugHostType.GetType, IDebugHostType::GetType, IDebugHostType.GetType
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
 - IDebugHostType::GetType
 - dbgmodel/IDebugHostType::GetType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType::GetType
---

# IDebugHostType::GetType


## -description

 Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.

## -parameters

### -param type

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

