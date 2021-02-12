---
UID: NF:dbgeng.IDebugEventContextCallbacks.Exception
tech.root: 
title: IDebugEventContextCallbacks::Exception
ms.date: 02/10/2021
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgeng.h
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
 - dbgeng.h
api_name:
 - IDebugEventContextCallbacks::Exception
f1_keywords:
 - IDebugEventContextCallbacks::Exception
 - dbgeng/IDebugEventContextCallbacks::Exception
dev_langs:
 - c++
---

## -description

Exceptions include breaks which cannot be mapped to an existing breakpoint instance.

Refer to [IDebugEventCallbacks::Exception](nf-dbgeng-idebugeventcallbacks-exception.md) for parameter description and additional information.

## -parameters

### -param Exception

### -param FirstChance

### -param Context [in]

Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)