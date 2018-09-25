---
UID: NF:dbgmodel.IDataModelScriptDebug.StartDebugging
title: IDataModelScriptDebug::StartDebugging
author: windows-driver-content
description: TBD
ms.assetid: 576517fd-8af5-4b1b-a49e-e77b4d72e2da
ms.author: windowsdriverdev
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug::StartDebugging, StartDebugging, IDataModelScriptDebug.StartDebugging, IDataModelScriptDebug::StartDebugging, IDataModelScriptDebug.StartDebugging
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
-	IDataModelScriptDebug.StartDebugging
product: Windows
targetos: Windows


---

# IDataModelScriptDebug::StartDebugging


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

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
