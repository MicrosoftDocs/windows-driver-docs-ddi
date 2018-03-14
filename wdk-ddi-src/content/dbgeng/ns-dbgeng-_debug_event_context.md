---
UID: NS:dbgeng._DEBUG_EVENT_CONTEXT
title: "_DEBUG_EVENT_CONTEXT"
author: windows-driver-content
description: Defines context information about an event.
old-location: debugger\debug_event_context.htm
old-project: debugger
ms.assetid: 3748675F-8187-4072-A0D0-3764B4D20288
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_EVENT_CONTEXT, DEBUG_EVENT_CONTEXT, DEBUG_EVENT_CONTEXT structure [Windows Debugging], PDEBUG_EVENT_CONTEXT, PDEBUG_EVENT_CONTEXT structure pointer [Windows Debugging], _DEBUG_EVENT_CONTEXT, dbgeng/DEBUG_EVENT_CONTEXT, dbgeng/PDEBUG_EVENT_CONTEXT, debugger.debug_event_context"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_EVENT_CONTEXT
product: Windows
targetos: Windows
req.typenames: DEBUG_EVENT_CONTEXT, *PDEBUG_EVENT_CONTEXT
---

# _DEBUG_EVENT_CONTEXT structure


## -description


Defines context information about an event.


## -syntax


````
typedef struct _DEBUG_EVENT_CONTEXT {
  ULONG Size;
  ULONG ProcessEngineId;
  ULONG ThreadEngineId;
  ULONG FrameEngineId;
} DEBUG_EVENT_CONTEXT, *PDEBUG_EVENT_CONTEXT;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541478">DEBUG_EVENT_XXX</a>



 

 


