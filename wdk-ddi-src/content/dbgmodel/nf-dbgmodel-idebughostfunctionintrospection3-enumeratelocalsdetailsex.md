---
UID: NF:dbgmodel.IDebugHostFunctionIntrospection3.EnumerateLocalsDetailsEx
tech.root: debugger
title: IDebugHostFunctionIntrospection3::EnumerateLocalsDetailsEx
ms.date: 01/29/2025
targetos: Windows
description: The EnumerateLocalsDetailsEx method enumerates a set of information about all locals and arguments within a function.
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
 - IDebugHostFunctionIntrospection3::EnumerateLocalsDetailsEx
f1_keywords:
 - IDebugHostFunctionIntrospection3::EnumerateLocalsDetailsEx
 - dbgmodel/IDebugHostFunctionIntrospection3::EnumerateLocalsDetailsEx
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateLocalsDetailsEx
---

## -description

The EnumerateLocalsDetailsEx method enumerates a set of information about all locals and arguments within a function. Optionally, it can also enumerate all locals and arguments of functions inlined within the given function if 'enumerateInlinedLocals' is true. If the 'enumerateInlinedLocals' argument is false, this method behaves similarly to [EnumerateLocalsDetails](nf-dbgmodel-idebughostfunctionintrospection2-enumeratelocalsdetails.md).

## -parameters

### -param enumerateInlinedLocals

A boolean value. If true, the method will enumerate locals and arguments of inlined functions; otherwise, it will not.

### -param localsEnum

A pointer to a pointer variable that receives the [IDebugHostFunctionLocalDetailsEnumerator interface](dbgmodel-idebughostfunctionlocaldetailsenumerator.md) of the enumerated locals details.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionIntrospection3 interface](nn-dbgmodel-idebughostfunctionintrospection3.md)