---
UID: NS:dbgeng._DEBUG_EVENT_CONTEXT
title: "_DEBUG_EVENT_CONTEXT"
author: windows-driver-content
description: Defines context information about an event.
old-location: debugger\debug_event_context.htm
old-project: debugger
ms.assetid: 3748675F-8187-4072-A0D0-3764B4D20288
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: DEBUG_EVENT_CONTEXT, DEBUG_EVENT_CONTEXT structure [Windows Debugging], PDEBUG_EVENT_CONTEXT structure pointer [Windows Debugging], *PDEBUG_EVENT_CONTEXT, PDEBUG_EVENT_CONTEXT, dbgeng/DEBUG_EVENT_CONTEXT, dbgeng/PDEBUG_EVENT_CONTEXT, debugger.debug_event_context, _DEBUG_EVENT_CONTEXT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	DbgEng.h
apiname:
-	DEBUG_EVENT_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PDEBUG_EVENT_CONTEXT, DEBUG_EVENT_CONTEXT"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_EVENT_CONTEXT structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

