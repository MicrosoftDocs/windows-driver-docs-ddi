---
UID: NF:dbgeng.IDebugEventContextCallbacks.Breakpoint
tech.root: debugger
title: IDebugEventContextCallbacks::Breakpoint
ms.date: 02/12/2021
ms.topic: language-reference
targetos: Windows
description: A breakpoint event is generated when a breakpoint exception is received and it can be mapped to an existing breakpoint.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgeng.h
req.idl: 
req.include-header: dbgeng.h
req.target-type: Desktop
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - IDebugEventContextCallbacks::Breakpoint
f1_keywords:
 - IDebugEventContextCallbacks::Breakpoint
 - dbgeng/IDebugEventContextCallbacks::Breakpoint
dev_langs:
 - c++
---

## -description

A breakpoint event is generated when a breakpoint exception is received and it can be mapped to an existing breakpoint.
The callback method is given a reference to the breakpoint and should release it when it is done with it.

Refer to [IDebugEventCallbacks::Breakpoint](nf-dbgeng-idebugeventcallbacks-breakpoint.md) for parameter description and additional information.

## -parameters

### -param Bp

[in]
Specifies a pointer to the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> object corresponding to the breakpoint that was triggered.

### -param Context

[in]
Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)
