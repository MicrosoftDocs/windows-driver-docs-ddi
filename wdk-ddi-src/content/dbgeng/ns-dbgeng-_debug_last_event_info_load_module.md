---
UID: NS:dbgeng._DEBUG_LAST_EVENT_INFO_LOAD_MODULE
title: "_DEBUG_LAST_EVENT_INFO_LOAD_MODULE"
author: windows-driver-content
description: Describes the load module of the last event.
old-location: debugger\debug_last_event_info_load_module.htm
old-project: debugger
ms.assetid: 0C2371FE-935A-499B-8E7C-09AA6C03FC90
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PDEBUG_LAST_EVENT_INFO_LOAD_MODULE, ,, A, B, D, DEBUG_LAST_EVENT_INFO_LOAD_MODULE, DEBUG_LAST_EVENT_INFO_LOAD_MODULE structure [Windows Debugging], E, F, G, I, L, M, N, O, P, PDEBUG_LAST_EVENT_INFO_LOAD_MODULE, PDEBUG_LAST_EVENT_INFO_LOAD_MODULE structure pointer [Windows Debugging], S, T, U, V, _, _DEBUG_LAST_EVENT_INFO_LOAD_MODULE, dbgeng/DEBUG_LAST_EVENT_INFO_LOAD_MODULE, dbgeng/PDEBUG_LAST_EVENT_INFO_LOAD_MODULE, debugger.debug_last_event_info_load_module"
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
-	DEBUG_LAST_EVENT_INFO_LOAD_MODULE
product: Windows
targetos: Windows
req.typenames: DEBUG_LAST_EVENT_INFO_LOAD_MODULE, *PDEBUG_LAST_EVENT_INFO_LOAD_MODULE
---

# _DEBUG_LAST_EVENT_INFO_LOAD_MODULE structure


## -description


Describes the load module of the last event.


## -syntax


````
typedef struct _DEBUG_LAST_EVENT_INFO_LOAD_MODULE {
  ULONG64 Base;
} DEBUG_LAST_EVENT_INFO_LOAD_MODULE, *PDEBUG_LAST_EVENT_INFO_LOAD_MODULE;
````


## -struct-fields




### -field Base

The base of the load module.

