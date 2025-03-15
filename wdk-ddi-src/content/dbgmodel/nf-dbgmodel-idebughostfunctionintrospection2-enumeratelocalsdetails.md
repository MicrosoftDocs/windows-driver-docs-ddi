---
UID: NF:dbgmodel.IDebugHostFunctionIntrospection2.EnumerateLocalsDetails
tech.root: debugger
title: IDebugHostFunctionIntrospection2::EnumerateLocalsDetails
ms.date: 01/29/2025
targetos: Windows
description: The EnumerateLocalsDetails method enumerates a set of information about all locals and arguments within a function.
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
 - IDebugHostFunctionIntrospection2::EnumerateLocalsDetails
f1_keywords:
 - IDebugHostFunctionIntrospection2::EnumerateLocalsDetails
 - dbgmodel/IDebugHostFunctionIntrospection2::EnumerateLocalsDetails
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateLocalsDetails
---

## -description

The EnumerateLocalsDetails method enumerates a set of information about all locals and arguments within a function. It doesn't enumerate any locals and arguments of functions inlined within the given function. To enumerate inlined functions, use the [EnumerateLocalsDetailsEx method](nf-dbgmodel-idebughostfunctionintrospection2-enumeratelocalsdetailsex.md) on the IDebugHostFunctionIntrospection2 interface.

## -parameters

### -param localsEnum

A pointer to a pointer variable that receives the [IDebugHostFunctionLocalDetailsEnumerator interface](nn-dbgmodel-idebughostfunctionlocaldetailsenumerator.md) of the enumerated locals details.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionIntrospection2 interface](nn-dbgmodel-idebughostfunctionintrospection2.md)