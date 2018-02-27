---
UID: NS:dbgeng._DEBUG_LAST_EVENT_INFO_EXCEPTION
title: "_DEBUG_LAST_EVENT_INFO_EXCEPTION"
author: windows-driver-content
description: Describes the exception of the last event.
old-location: debugger\debug_last_event_info_exception.htm
old-project: debugger
ms.assetid: FB4EBA71-5144-440A-AFD1-7460903C9189
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PDEBUG_LAST_EVENT_INFO_EXCEPTION, DEBUG_LAST_EVENT_INFO_EXCEPTION, DEBUG_LAST_EVENT_INFO_EXCEPTION structure [Windows Debugging], PDEBUG_LAST_EVENT_INFO_EXCEPTION, PDEBUG_LAST_EVENT_INFO_EXCEPTION structure pointer [Windows Debugging], _DEBUG_LAST_EVENT_INFO_EXCEPTION, dbgeng/DEBUG_LAST_EVENT_INFO_EXCEPTION, dbgeng/PDEBUG_LAST_EVENT_INFO_EXCEPTION, debugger.debug_last_event_info_exception"
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
-	DEBUG_LAST_EVENT_INFO_EXCEPTION
product: Windows
targetos: Windows
req.typenames: DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION
---

# _DEBUG_LAST_EVENT_INFO_EXCEPTION structure


## -description


Describes the exception of the last event.


## -syntax


````
typedef struct _DEBUG_LAST_EVENT_INFO_EXCEPTION {
  EXCEPTION_RECORD64 ExceptionRecord;
  ULONG              FirstChance;
} DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION;
````


## -struct-fields




### -field ExceptionRecord

An exception record.


### -field FirstChance

A first chance value.

