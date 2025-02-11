---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails2.IsInlineScope
tech.root: debugger
title: IDebugHostFunctionLocalDetails2::IsInlineScope
ms.date: 01/29/2025
targetos: Windows
description: The IsInlineScope method determines if the local variable is scoped within an inlined function.
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
 - IDebugHostFunctionLocalDetails2::IsInlineScope
f1_keywords:
 - IDebugHostFunctionLocalDetails2::IsInlineScope
 - dbgmodel/IDebugHostFunctionLocalDetails2::IsInlineScope
dev_langs:
 - c++
helpviewer_keywords:
 - IsInlineScope
---

## -description

The IsInlineScope method determines if the local variable is scoped within an inlined function. This will always return false unless the [IDebugHostFunctionLocalDetailsEnumerator::EnumerateLocalsDetailsEx method](nf-dbgmodel-idebughostfunctionlocaldetailsenumerator-enumeratelocalsdetailsex.md) is called with 'enumerateInlinedLocals' set to true.

## -returns

Returns a boolean value. If the local variable is scoped within an inlined function, it returns true. Otherwise, it returns false.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetails2 interface](nn-dbgmodel-idebughostfunctionlocaldetails2.md)