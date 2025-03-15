---
UID: NF:dbgmodel.IDebugHostFunctionIntrospection3.IsNoReturnFunction
tech.root: debugger
title: IDebugHostFunctionIntrospection3::IsNoReturnFunction
ms.date: 01/29/2025
targetos: Windows
description: The IsNoReturnFunction method determines if the function is a non-returning function.
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
 - IDebugHostFunctionIntrospection3::IsNoReturnFunction
f1_keywords:
 - IDebugHostFunctionIntrospection3::IsNoReturnFunction
 - dbgmodel/IDebugHostFunctionIntrospection3::IsNoReturnFunction
dev_langs:
 - c++
helpviewer_keywords:
 - IsNoReturnFunction
---

## -description

The IsNoReturnFunction method determines if the function is a non-returning function.

## -parameters

### -param pIsNoReturnFunction

A pointer to a boolean variable that receives the flagged value from the method. The result will be true if the function is a non-returning function, and false otherwise.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionIntrospection3 interface](nn-dbgmodel-idebughostfunctionintrospection3.md)