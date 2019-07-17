---
UID: NF:dbgmodel.IDataModelScriptDebug2.GetDebugState
title: IDataModelScriptDebug2::GetDebugState (dbgmodel.h)
description: The GetDebugState method returns the current state of the script (that is whether it is executing or not). 
ms.assetid: 5426937e-cf7e-4af0-afe3-39b2dce07983
ms.date: 08/21/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug2.GetDebugState"
ms.keywords: IDataModelScriptDebug2::GetDebugState, GetDebugState, IDataModelScriptDebug2.GetDebugState, IDataModelScriptDebug2::GetDebugState, IDataModelScriptDebug2.GetDebugState
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptDebug2.GetDebugState
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug2::GetDebugState


## -description
The GetDebugState method returns the current state of the script (e.g.: whether it is executing or not). The state is defined by a value within the ScriptDebugState enumeration which is defined as follows.

Enumerant |	Description
|---------|-------------|
ScriptDebugNoDebugger |	Indicates that debugging is not active on the script. This means that the StartDebugging method has not yet been called on this script or that StopDebugging has already been called. In either case, further interaction with the script debugger on the given script is invalid until the debugger is started.
ScriptDebugNotExecuting |	Indicates that no code within the script is actively executing. Returning this as opposed to ScriptDebugNoDebugger indicates that the script is being debugged -- that is, the StartDebugging method has been successfully called on its debug interface.
ScriptDebugExecuting |	Indicates that the script is actively executing code and is not broken into the debugger.
ScriptDebugBreak |	Indicates that the script is broken into the debugger during the execution of code within the script



## -parameters


## -returns
The debug state of the script as indicated by a value in the ScriptDebugState enumeration.

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)
