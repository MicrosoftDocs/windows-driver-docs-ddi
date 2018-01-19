---
UID: NS:dbgeng._DEBUG_LAST_EVENT_INFO_BREAKPOINT
title: _DEBUG_LAST_EVENT_INFO_BREAKPOINT
author: windows-driver-content
description: Describes the breakpoint of the last event.
old-location: debugger\debug_last_event_info_breakpoint.htm
old-project: debugger
ms.assetid: DAE22E2C-E8A9-4FF0-B9E9-D652C4E7B0B8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_LAST_EVENT_INFO_BREAKPOINT, DEBUG_LAST_EVENT_INFO_BREAKPOINT, *PDEBUG_LAST_EVENT_INFO_BREAKPOINT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_LAST_EVENT_INFO_BREAKPOINT
req.alt-loc: DbgEng.h
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
req.typenames: DEBUG_LAST_EVENT_INFO_BREAKPOINT, *PDEBUG_LAST_EVENT_INFO_BREAKPOINT
---

# _DEBUG_LAST_EVENT_INFO_BREAKPOINT structure



## -description
Describes the breakpoint of the last event.



## -syntax

````
typedef struct _DEBUG_LAST_EVENT_INFO_BREAKPOINT {
  ULONG Id;
} DEBUG_LAST_EVENT_INFO_BREAKPOINT, *PDEBUG_LAST_EVENT_INFO_BREAKPOINT;
````


## -struct-fields

### -field Id

The ID of the breakpoint.


## -remarks
