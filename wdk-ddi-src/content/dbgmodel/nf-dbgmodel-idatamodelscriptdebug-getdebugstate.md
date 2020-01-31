---
UID: NF:dbgmodel.IDataModelScriptDebug.GetDebugState
title: IDataModelScriptDebug::GetDebugState (dbgmodel.h)
description: The GetDebugState method returns the current state of the script (whether it is executing or not). 
ms.assetid: 718209b9-68ab-43eb-a944-6aad95db4e3d
ms.date: 08/21/2018
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug.GetDebugState"
ms.keywords: IDataModelScriptDebug::GetDebugState, GetDebugState, IDataModelScriptDebug.GetDebugState, IDataModelScriptDebug::GetDebugState, IDataModelScriptDebug.GetDebugState
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
- IDataModelScriptDebug.GetDebugState
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug::GetDebugState


## -description

The GetDebugState method returns the current state of the script (e.g.: whether it is executing or not). The state is defined by a value within the ScriptDebugState enumeration which is defined as follows.

Enumerant |	Description
|---------|-------------|
ScriptDebugNoDebugger |	Indicates that debugging is not active on the script. This means that the StartDebugging method has not yet been called on this script or that StopDebugging has already been called. In either case, further interaction with the script debugger on the given script is invalid until the debugger is started.
ScriptDebugNotExecuting |	Indicates that no code within the script is actively executing. Returning this as opposed to ScriptDebugNoDebugger indicates that the script is being debugged -- that is, the StartDebugging method has been successfully called on its debug interface.
ScriptDebugExecuting |	Indicates that the script is actively executing code and is not broken into the debugger.
ScriptDebugBreak |	Indicates that the script is broken into the debugger during the execution of code within the script



## -returns
The debug state of the script as indicated by a value in the ScriptDebugState enumeration.

## -remarks

## -see-also

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
