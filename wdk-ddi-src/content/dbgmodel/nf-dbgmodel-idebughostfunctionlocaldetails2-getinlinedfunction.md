---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails2.GetInlinedFunction
tech.root: debugger
title: IDebugHostFunctionLocalDetails2::GetInlinedFunction
ms.date: 01/29/2025
targetos: Windows
description: The GetInlinedFunction method retrieves a symbol for the inlined function that the local variable is contained within, if IsInlineScope() returns true.
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
 - IDebugHostFunctionLocalDetails2::GetInlinedFunction
f1_keywords:
 - IDebugHostFunctionLocalDetails2::GetInlinedFunction
 - dbgmodel/IDebugHostFunctionLocalDetails2::GetInlinedFunction
dev_langs:
 - c++
helpviewer_keywords:
 - GetInlinedFunction
---

## -description

The GetInlinedFunction method retrieves a symbol for the inlined function that the local variable is contained within, if [IsInlineScope()](nf-dbgmodel-idebughostfunctionlocaldetails2-isinlinescope.md) returns true.

## -parameters

### -param inlineFunction

A pointer to a pointer variable that receives the [IDebugHostSymbol interface](nn-dbgmodel-idebughostsymbol.md) of the inlined function.

## -returns

If the method succeeds and the local is within an inlined scope, it returns S_OK and a pointer to the inlined function symbol. If the local is not within an inlined scope, it returns an E_FAIL. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetails2 interface](nn-dbgmodel-idebughostfunctionlocaldetails2.md)