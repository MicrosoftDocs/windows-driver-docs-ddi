---
UID: NF:dbgmodel.IDebugHostType3.GetGenericArgumentCount
tech.root: debugger
title: IDebugHostType3::GetGenericArgumentCount
ms.date: 01/26/2025
targetos: Windows
description: The GetGenericArgumentCount method, when called on a type, gets the number of generic arguments to the type.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType3::GetGenericArgumentCount
f1_keywords:
 - IDebugHostType3::GetGenericArgumentCount
 - dbgmodel/IDebugHostType3::GetGenericArgumentCount
dev_langs:
 - c++
helpviewer_keywords:
 - GetGenericArgumentCount
---

## -description

Returns the number of arguments to the generic/template.  The returned value must be greater than zero.

## -parameters

### -param argCount

The number of generic arguments (e.g.: template arguments) to the type will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)