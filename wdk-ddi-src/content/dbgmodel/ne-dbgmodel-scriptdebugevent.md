---
UID: NE:dbgmodel.ScriptDebugEvent
title: ScriptDebugEvent
author: windows-driver-content
description: 
ms.assetid: 79741ba7-a920-4f0e-a953-9ff6a0a8ee85
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: ScriptDebugEvent, , 
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	ScriptDebugEvent
product: Windows
targetos: Windows
tech.root: debugger
---

# ScriptDebugEvent enumeration

## -description

Defines what debug event occurred.

A debug event is defined by a variant record known as a ScriptDebugEventInformation. Which fields in the event information are valid is largely defined by the DebugEvent member. It defines the kind of event which occurred as described by a member of the ScriptDebugEvent enumeration.
  
  
## -enum-fields

### -field ScriptDebugBreakpoint
Indicates that a breakpoint was hit. Information about the particular breakpoint which was hit is contained in the BreakpointInformation portion of the union which contains the following: 

- BreakpointId: The unique identifier for the breakpoint which was hit.

### -field ScriptDebugStep 
Indicates that a step event occurred. No further information is provided.

### -field ScriptDebugException 
Indicates that an exception occurred. Information about the particular exception which occurred is contained in the ExceptionInformaiton position of the union which contains the following:

- IsUncaught: Indicates whether or not the breakpoint is a first-chance (false) or an unhandled exception (true)

The data object for the event is the object which was thrown. 

The ScriptDebugEventInformation will fill in .u.ExceptionInformation and the outpassed object is a data model conversion of the actual exception.
    

### -field ScriptDebugAsyncBreak 
Indicates that an asynchronous break into the script occurred. This might be because of something like "break on entry" or "break on event"

## -remarks

Whenever any event occurs which breaks into the script debugger, the debug code itself makes a call to the interface via the NotifyDebugEvent method. This method is synchronous. No execution of the script will resume until the interface returns from the event. The definition of the script debugger is intended to be simple: there are absolutely no nested events requiring processing. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
