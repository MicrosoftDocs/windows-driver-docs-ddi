---
UID: NF:dbgeng.IDebugEventContextCallbacks.ChangeDebuggeeState
tech.root: debugger
title: IDebugEventContextCallbacks::ChangeDebuggeeState
ms.date: 02/12/2021
ms.topic: language-reference
targetos: Windows
description: Debuggee state, such as registers or data spaces, has changed.
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
 - IDebugEventContextCallbacks::ChangeDebuggeeState
f1_keywords:
 - IDebugEventContextCallbacks::ChangeDebuggeeState
 - dbgeng/IDebugEventContextCallbacks::ChangeDebuggeeState
dev_langs:
 - c++
---

## -description

Debuggee state, such as registers or data spaces, has changed.

This is an informational callback notifying the provider about changes in debug state.  The return value of this callbacks is ignored.  Implementations can not call back into the engine.

Refer to [IDebugEventCallbacks::ChangeDebuggeeState](nf-dbgeng-idebugeventcallbacks-changedebuggeestate.md) for parameter description and additional information.

## -parameters

### -param Flags

### -param Argument

### -param Context [in]

Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)