---
UID: NF:dbgeng.IDebugEventContextCallbacks.SystemError
tech.root: debugger
title: IDebugEventContextCallbacks::SystemError
ms.date: 02/12/2021
ms.topic: language-reference
targetos: Windows
description: The SystemError callback method is called by the engine when a system error occurs in the target. This method belongs to IDebugEventContextCallbacks.
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
 - IDebugEventContextCallbacks::SystemError
f1_keywords:
 - IDebugEventContextCallbacks::SystemError
 - dbgeng/IDebugEventContextCallbacks::SystemError
dev_langs:
 - c++
---

## -description

The SystemError callback method is called by the engine when a system error occurs in the target.

Refer to [IDebugEventCallbacks::SystemError](nf-dbgeng-idebugeventcallbacks-systemerror.md) for parameter description and additional information.

## -parameters

### -param Error

### -param Level

### -param Context [in]

Specifies the [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains additional information about the debug event that occurred.

### -param ContextSize [in]

Specifies the size of the buffer Context.

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)