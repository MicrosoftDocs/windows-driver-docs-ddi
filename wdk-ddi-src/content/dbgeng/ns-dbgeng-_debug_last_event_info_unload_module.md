---
UID: NS:dbgeng._DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE
title: "_DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE"
author: windows-driver-content
description: Describes the unload module of the last event.
old-location: debugger\debug_last_event_info_unload_module.htm
old-project: Debugger
ms.assetid: D569C1DD-0ACB-41AA-8589-BD4332006CA2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, *PDEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, dbgeng/DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, dbgeng/PDEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE structure [Windows Debugging], PDEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, PDEBUG_LAST_EVENT_INFO_UNLOAD_MODULE structure pointer [Windows Debugging], debugger.debug_last_event_info_unload_module"
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
-	DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE
product: Windows
targetos: Windows
req.typenames: DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, *PDEBUG_LAST_EVENT_INFO_UNLOAD_MODULE
---

# _DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE structure


## -description


Describes the unload module of the last event. 


## -syntax


````
typedef struct _DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE {
  ULONG64 Base;
} DEBUG_LAST_EVENT_INFO_UNLOAD_MODULE, *PDEBUG_LAST_EVENT_INFO_UNLOAD_MODULE;
````


## -struct-fields




### -field Base

The base of the unload module.

