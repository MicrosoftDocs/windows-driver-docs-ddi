---
UID: NS:dbgeng._DEBUG_CACHED_SYMBOL_INFO
title: "_DEBUG_CACHED_SYMBOL_INFO"
author: windows-driver-content
description: Defines information about cached symbols.
old-location: debugger\debug_cached_symbol_info.htm
old-project: Debugger
ms.assetid: CC7914B6-DCE1-45D1-84D3-5FF1449AD565
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: DEBUG_CACHED_SYMBOL_INFO, *PDEBUG_CACHED_SYMBOL_INFO, DEBUG_CACHED_SYMBOL_INFO structure [Windows Debugging], dbgeng/DEBUG_CACHED_SYMBOL_INFO, _DEBUG_CACHED_SYMBOL_INFO, debugger.debug_cached_symbol_info, PDEBUG_CACHED_SYMBOL_INFO structure pointer [Windows Debugging], PDEBUG_CACHED_SYMBOL_INFO, dbgeng/PDEBUG_CACHED_SYMBOL_INFO
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
-	DEBUG_CACHED_SYMBOL_INFO
product: Windows
targetos: Windows
req.typenames: "*PDEBUG_CACHED_SYMBOL_INFO, DEBUG_CACHED_SYMBOL_INFO"
---

# _DEBUG_CACHED_SYMBOL_INFO structure


## -description


Defines information about cached symbols.


## -syntax


````
typedef struct _DEBUG_CACHED_SYMBOL_INFO {
  ULONG64 ModBase;
  ULONG64 Arg1;
  ULONG64 Arg2;
  ULONG   Id;
  ULONG   Arg3;
} DEBUG_CACHED_SYMBOL_INFO, *PDEBUG_CACHED_SYMBOL_INFO;
````


## -struct-fields




### -field ModBase

A module base.


### -field Arg1

An argument value.


### -field Arg2

An argument value.


### -field Id

An ID.


### -field Arg3

An argument value.

