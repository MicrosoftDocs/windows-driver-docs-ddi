---
UID: NF:dbgmodel.IDebugHostContextControl.SwitchTo
tech.root: debugger
title: IDebugHostContextControl::SwitchTo
ms.date: 01/15/2025
targetos: Windows
description: The SwitchTo method switches the context to the specified context.
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
 - IDebugHostContextControl::SwitchTo
f1_keywords:
 - IDebugHostContextControl::SwitchTo
 - dbgmodel/IDebugHostContextControl::SwitchTo
dev_langs:
 - c++
helpviewer_keywords:
 - SwitchTo
---

## -description

The method SwitchTo() changes or switches the debugger engine context to IDebugHostContext. IDebugHostContext is the context from which IDebugHostContextControl was originally retrieved. This is considered a "full" context debugger engine swit

## -returns

Returns an HRESULT indicating the success or failure of the method. 

## -remarks

## -see-also

[IDebugHostContextControl interface](nn-dbgmodel-idebughostcontextcontrol.md)