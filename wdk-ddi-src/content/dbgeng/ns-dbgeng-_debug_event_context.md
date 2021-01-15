---
UID: NS:dbgeng._DEBUG_EVENT_CONTEXT
title: _DEBUG_EVENT_CONTEXT (dbgeng.h)
description: Defines context information about an event.
old-location: debugger\debug_event_context.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["DEBUG_EVENT_CONTEXT structure"]
ms.keywords: "*PDEBUG_EVENT_CONTEXT, DEBUG_EVENT_CONTEXT, DEBUG_EVENT_CONTEXT structure [Windows Debugging], PDEBUG_EVENT_CONTEXT, PDEBUG_EVENT_CONTEXT structure pointer [Windows Debugging], _DEBUG_EVENT_CONTEXT, dbgeng/DEBUG_EVENT_CONTEXT, dbgeng/PDEBUG_EVENT_CONTEXT, debugger.debug_event_context"
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: DEBUG_EVENT_CONTEXT, *PDEBUG_EVENT_CONTEXT
f1_keywords:
 - _DEBUG_EVENT_CONTEXT
 - dbgeng/_DEBUG_EVENT_CONTEXT
 - PDEBUG_EVENT_CONTEXT
 - dbgeng/PDEBUG_EVENT_CONTEXT
 - DEBUG_EVENT_CONTEXT
 - dbgeng/DEBUG_EVENT_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - _DEBUG_EVENT_CONTEXT
 - PDEBUG_EVENT_CONTEXT
 - DEBUG_EVENT_CONTEXT
---

# _DEBUG_EVENT_CONTEXT structure


## -description

Defines context information about an event.

## -struct-fields

### -field Size

The size of the event.

### -field ProcessEngineId

The process engine ID of the event.

### -field ThreadEngineId

The process thread ID of the event.

### -field FrameEngineId

The frame engine ID of the event.

## -see-also

<a href="/previous-versions/ff541478(v=vs.85)">DEBUG_EVENT_XXX</a>

