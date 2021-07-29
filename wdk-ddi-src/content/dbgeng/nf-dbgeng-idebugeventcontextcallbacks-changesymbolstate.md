---
UID: NF:dbgeng.IDebugEventContextCallbacks.ChangeSymbolState
tech.root: debugger
title: IDebugEventContextCallbacks::ChangeSymbolState
ms.date: 02/12/2021
targetos: Windows
description: The symbol state has changed.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgeng.h
req.idl: 
req.include-header: dbgeng.h
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
 - dbgeng.h
api_name:
 - IDebugEventContextCallbacks::ChangeSymbolState
f1_keywords:
 - IDebugEventContextCallbacks::ChangeSymbolState
 - dbgeng/IDebugEventContextCallbacks::ChangeSymbolState
dev_langs:
 - c++
---

## -description

The symbol state has changed.

This is an informational callback notifying the provider about changes in debug state.  The return value of this callbacks is ignored.  Implementations can not call back into the engine.

Refer to [IDebugEventCallbacks::ChangeSymbolState](nf-dbgeng-idebugeventcallbacks-changesymbolstate.md) for parameter description and additional information.

## -parameters

### -param Flags

### -param Argument

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)