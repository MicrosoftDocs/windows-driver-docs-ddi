---
UID: NF:dbgeng.IDebugEventContextCallbacks.ExitProcess
tech.root: debugger
title: IDebugEventContextCallbacks::ExitProcess
ms.date: 02/12/2021
ms.topic: language-reference
targetos: Windows
description: The ExitProcess callback method is called by the engine when an exit-process debugging event occurs in the target.
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
 - IDebugEventContextCallbacks::ExitProcess
f1_keywords:
 - IDebugEventContextCallbacks::ExitProcess
 - dbgeng/IDebugEventContextCallbacks::ExitProcess
dev_langs:
 - c++
---

## -description

The <b>ExitProcess</b> callback method is called by the engine when an exit-process debugging event occurs in the target.

Refer to [IDebugEventCallbacks::ExitProcess](nf-dbgeng-idebugeventcallbacks-exitprocess.md) for parameter description and additional information.

## -parameters

### -param ExitCode

### -param Context [in]

Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)