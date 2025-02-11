---
UID: NF:dbgmodel.IDebugHostType3.GetFunctionInstancePointerType
tech.root: debugger
title: IDebugHostType3::GetFunctionInstancePointerType
ms.date: 01/26/2025
targetos: Windows
description: The GetFunctionInstancePointerType method returns the type of a function instance pointer.
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
 - IDebugHostType3::GetFunctionInstancePointerType
f1_keywords:
 - IDebugHostType3::GetFunctionInstancePointerType
 - dbgmodel/IDebugHostType3::GetFunctionInstancePointerType
dev_langs:
 - c++
helpviewer_keywords:
 - GetFunctionInstancePointerType
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)