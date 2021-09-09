---
UID: NF:dbgeng.IDebugEventContextCallbacks.UnloadModule
tech.root: debugger
title: IDebugEventContextCallbacks::UnloadModule
ms.date: 02/12/2021
targetos: Windows
description: The IDebugEventContextCallbacks::UnloadModule callback method is called by the engine when a module-unload debugging event occurs in the target.
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
 - IDebugEventContextCallbacks::UnloadModule
f1_keywords:
 - IDebugEventContextCallbacks::UnloadModule
 - dbgeng/IDebugEventContextCallbacks::UnloadModule
dev_langs:
 - c++
---

## -description

The UnloadModule callback method is called by the engine when a module-unload debugging event occurs in the target.

Refer to [IDebugEventCallbacks::UnloadModule](nf-dbgeng-idebugeventcallbacks-unloadmodule.md) for parameter description and additional information.

## -parameters

### -param ImageBaseName

### -param BaseOffset

### -param Context [in]

Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)