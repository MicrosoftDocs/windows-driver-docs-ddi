---
UID: NF:dbgmodel.IDebugHostType2.GetGenericArgumentCount
title: IDebugHostType2::GetGenericArgumentCount (dbgmodel.h)
description: Returns the number of arguments to the generic/template.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetGenericArgumentCount"]
ms.keywords: IDebugHostType2::GetGenericArgumentCount, GetGenericArgumentCount, IDebugHostType2.GetGenericArgumentCount, IDebugHostType2::GetGenericArgumentCount, IDebugHostType2.GetGenericArgumentCount
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
 - IDebugHostType2::GetGenericArgumentCount
 - dbgmodel/IDebugHostType2::GetGenericArgumentCount
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetGenericArgumentCount
---

# IDebugHostType2::GetGenericArgumentCount


## -description

Returns the number of arguments to the generic/template.  The returned value must be greater than zero.

## -parameters

### -param argCount

The number of generic arguments (e.g.: template arguments) to the type will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

