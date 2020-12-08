---
UID: NF:dbgmodel.IDebugHostType2.GetType
title: IDebugHostType2::GetType (dbgmodel.h)
description: Returns the type (e.g. "int *") of the symbol if the symbol has a type.
ms.date: 09/21/2018
keywords: ["IDebugHostType2::GetType"]
ms.keywords: IDebugHostType2::GetType, GetType, IDebugHostType2.GetType, IDebugHostType2::GetType, IDebugHostType2.GetType
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
 - IDebugHostType2::GetType
 - dbgmodel/IDebugHostType2::GetType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetType
---

# IDebugHostType2::GetType


## -description

Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.

## -parameters

### -param type

The type of the symbol will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

