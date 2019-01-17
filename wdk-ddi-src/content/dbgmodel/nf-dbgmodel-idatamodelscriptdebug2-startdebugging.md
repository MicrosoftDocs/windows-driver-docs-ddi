---
UID: NF:dbgmodel.IDataModelScriptDebug2.StartDebugging
title: IDataModelScriptDebug2::StartDebugging
description: The StartDebugging method "turns on" the debugger for a particular script. 
ms.assetid: 2cebdd6c-9883-492a-881d-f3b9175804f2
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug2::StartDebugging, StartDebugging, IDataModelScriptDebug2.StartDebugging, IDataModelScriptDebug2::StartDebugging, IDataModelScriptDebug2.StartDebugging
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
-	IDataModelScriptDebug2.StartDebugging
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug2::StartDebugging


## -description

The StartDebugging method "turns on" the debugger for a particular script. The act of starting debugging does not actively cause any execution break or stepping. It merely makes the script debuggable and provides a set of interfaces for the client to communicate with the debugging interface. 

The debug client which is passed to the StartDebugging method must be saved by the implementation. When any event occurs that "breaks into the debugger", that break is implemented by a synchronous call to notify the client of the event. Execution resumes when the client returns from notification call. A return argument indicates how execution should resume. 

This method should only be called when the script debugger is not enabled for the given script. Any other call is illegal. 


## -parameters

### -param debugClient
An interface to the client of the script debugger. Debug events are passed to this interface.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)
