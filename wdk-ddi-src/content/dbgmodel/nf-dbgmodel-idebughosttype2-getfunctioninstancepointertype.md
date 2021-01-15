---
UID: NF:dbgmodel.IDebugHostType2.GetFunctionInstancePointerType
title: IDebugHostType2::GetFunctionInstancePointerType (dbgmodel.h)
description: Indicates what the type of the instance ("this") pointer passed to the function is.
ms.date: 10/04/2018
keywords: ["IDebugHostType2::GetFunctionInstancePointerType"]
ms.keywords: IDebugHostType2::GetFunctionInstancePointerType, GetFunctionInstancePointerType, IDebugHostType2.GetFunctionInstancePointerType, IDebugHostType2::GetFunctionInstancePointerType, IDebugHostType2.GetFunctionInstancePointerType
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
 - IDebugHostType2::GetFunctionInstancePointerType
 - dbgmodel/IDebugHostType2::GetFunctionInstancePointerType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetFunctionInstancePointerType
---

# IDebugHostType2::GetFunctionInstancePointerType


## -description

Indicates what the type of the instance ("this") pointer passed to the function is.  This method will fail
if the function is not an instance method on a class.

## -parameters

### -param instancePointerType

The instance pointer type.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

