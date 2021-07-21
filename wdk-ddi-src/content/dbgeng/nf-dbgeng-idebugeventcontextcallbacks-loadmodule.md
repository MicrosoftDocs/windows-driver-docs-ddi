---
UID: NF:dbgeng.IDebugEventContextCallbacks.LoadModule
tech.root: debugger
title: IDebugEventContextCallbacks::LoadModule
ms.date: 02/12/2021
ms.topic: language-reference
targetos: Windows
description: The IDebugEventContextCallbacks::LoadModule callback method is called by the engine when a module-load debugging event occurs in the target.
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
 - IDebugEventContextCallbacks::LoadModule
f1_keywords:
 - IDebugEventContextCallbacks::LoadModule
 - dbgeng/IDebugEventContextCallbacks::LoadModule
dev_langs:
 - c++
---

## -description

The LoadModule callback method is called by the engine when a module-load debugging event occurs in the target.

Refer to [IDebugEventCallbacks::LoadModule](nf-dbgeng-idebugeventcallbacks-loadmodule.md) for parameter description and additional information.

## -parameters

Any of these values may be zero.

### -param ImageFileHandle

### -param BaseOffset

### -param ModuleSize

### -param ModuleName

### -param ImageName

### -param CheckSum

### -param TimeDateStamp

### -param Context [in]

Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)