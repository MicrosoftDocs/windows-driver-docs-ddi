---
UID: NE:dbgmodel.ScriptDebugEventFilter
title: ScriptDebugEventFilter (dbgmodel.h)
description: Defines what debug event occurred.
ms.assetid: c1778753-7c0d-4bd3-b817-19ece139a0ea
ms.date: 07/16/2018
keywords: ["ScriptDebugEventFilter enumeration"]
ms.keywords: ScriptDebugEventFilter, ,
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - ScriptDebugEventFilter
 - dbgmodel/ScriptDebugEventFilter
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - ScriptDebugEventFilter
---

# ScriptDebugEventFilter enumeration


## -description

Defines the set of debug events / exceptions which the script debugger can (potentially) auto-break on.

## -enum-fields

### -field ScriptDebugEventFilterEntry

Indicates that a break on *EVERY ENTRY* into the script from outside should break into the debugger.

### -field ScriptDebugEventFilterException 

Indicates that any first chance exception should immediately break into the debugger.

### -field ScriptDebugEventFilterUnhandledException 

ScriptDebugEventFilterUnhandledException: Indicates that unhandled exceptions should immediately break into the debugger.

### -field ScriptDebugEventFilterAbort 

Indicates that an abort (core debugger BREAK/STOP this action) should break into the script debugger rather than aborting the script execution.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

