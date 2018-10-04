---
UID: NF:dbgmodel.IDataModelScriptDebugClient.NotifyDebugEvent
title: IDataModelScriptDebugClient::NotifyDebugEvent
author: windows-driver-content
description: Whenever any event occurs which breaks into the script debugger, the debug code itself makes a call to the interface via the NotifyDebugEvent method. 
ms.assetid: 97e8fde7-949a-4e5d-bb84-49adb72b71af
ms.author: windowsdriverdev
ms.date: 09/10/2018
ms.topic: method
ms.keywords: IDataModelScriptDebugClient::NotifyDebugEvent, NotifyDebugEvent, IDataModelScriptDebugClient.NotifyDebugEvent, IDataModelScriptDebugClient::NotifyDebugEvent, IDataModelScriptDebugClient.NotifyDebugEvent
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelScriptDebugClient.NotifyDebugEvent
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptDebugClient::NotifyDebugEvent


## -description

Whenever any event occurs which breaks into the script debugger, the debug code itself makes a call to the interface via the NotifyDebugEvent method. This method is synchronous. No execution of the script will resume until the interface returns from the event. The definition of the script debugger is intended to be simple: there are absolutely no nested events requiring processing. 

A debug event is defined by a variant record known as a ScriptDebugEventInformation. Which fields in the event information are valid is largely defined by the DebugEvent member. 

It defines the kind of event which occurred as described by a member of the ScriptDebugEvent enumeration: 

Enumerant	| Description
|----------|-----------|
ScriptDebugBreakpoint	|  Indicates that a breakpoint was hit. Information about the particular breakpoint which was hit is contained in the BreakpointInformation portion of the union which contains the following: •	BreakpointId: The unique identifier for the breakpoint which was hit.
ScriptDebugStep		| Indicates that a step event occurred. No further information is provided.
ScriptDebugException 	| 	Indicates that an exception occurred. Information about the particular exception which occurred is contained in the ExceptionInformaiton position of the union which contains the following: •	IsUncaught: Indicates whether or not the breakpoint is a first-chance (false) or an unhandled exception (true). The data object for the event is the object which was thrown. 
ScriptDebugAsyncBreak 	| Indicates that an asynchronous break into the script occurred. This might be because of something like "break on entry" or "break on event"

When the interface decides how it wants to proceed from the debug event, it fills in the resumeEventKind argument and returns successfully from the NotifyDebugEvent method. How the debugger proceeds depends on the value in this field. It is a member of the ScriptExecutionKind enumeration defined as follows: 

Enumerant	| Description
|----------|-----------|
ScriptExecutionNormal	| Indicates that the interface would like the script to execute normally until the next debug event. This is the equivalent of a "go" command in a debugger UI.
ScriptExecutionStepIn	| Indicates that the interface would like the script debugger to step in and notify the interface when the step in has successfully completed. Note that other events may occur in the interim. In that case, there may never be a step notification.
ScriptDebugStepOut	| Indicates that the interface would like the script debugger to step out and notify the interface when the step out has successfully completed. Note that other events may occur in the interim. In that case, there may never be a step notification.
ScriptDebugStepOver	| Indicates that the interface would like the script debugger to step over and notify the interface when the step over has successfully completed. Note that other events may occur in the interim. In that case, there may never be a step notification




## -parameters

### -param pEventInfo
A data structure indicating what debug event has just occurred.

### -param pScript
The script in which the event occurred.

### -param pEventDataObject
The data object for the event in question. If the event has no data object, nullptr is passed. A data object is, for example, the exception object which was thrown for an exception notification.

### -param resumeEventKind
An indication from the interface to the debugger of how the debugger should resume execution of script code after the processing of the debug event. Such is returned as a member of the ScriptExecutionKind enumeration as described above.

## -returns
This method returns HRESULT that indicates success or failure.
## -remarks

## -see-also

[IDataModelScriptDebugClient interface](nn-dbgmodel-idatamodelscriptdebugclient.md)
