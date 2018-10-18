---
UID: NF:dbgmodel.IDataModelScript.Execute
title: IDataModelScript::Execute
author: windows-driver-content
description: The Execute method executes the content of the script as dictated by the last successful Populate call and modifies the object model of the debugger according to that content.
ms.assetid: 6682b609-fd29-4878-b820-f7a582b7295d
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScript::Execute, Execute, IDataModelScript.Execute, IDataModelScript::Execute, IDataModelScript.Execute
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
-	IDataModelScript.Execute
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScript::Execute


## -description

The Execute method executes the content of the script as dictated by the last successful Populate call and modifies the object model of the debugger according to that content. If the language (or the script provider) defines a "main function" -- one that the author would want called upon clicking an imaginary "Execute Script" button in a user interface -- such "main function" is not called during an Execute operation. The Execute operation can be considered to perform initialization and object model manipulations only (e.g.: executing root code and setting up extensibility points). 
Execution of a script is a two way communication between the script provider and the script client. Errors, debugging control, and other semantics are passed across the communication channel between IDataModelScript and IDataModelScriptClient.

Depending on whether the Execute operation succeeds or fails, one of two things should happen: 

**For a successful return:** 

o	The previously executed content of the script is flushed and forgotten

o	Any object model manipulations or extensibility points changed as a result of the prior execution of the script are undone

o	The object model manipulations and extensibility points of the new execution of the script are active

**For a failed return:** 

o	Any manipulations or extensibility points of the new attempted execution of the script are undone

o	The prior state of the script is restored. All its object model manipulations and extensibility points are restored.

o	The state should be as it was after the successful Populate call but before any Execute call

Note that for a properly written script provider and scripting environment, calling the Execute method multiple times without an intervening call to Populate or Unlink 'should be idempotent. That is, calling Execute N times in a row should appear to the user the same as calling Execute once. The execution should not produce side effecting results on the state of the debug target. Subsequently utilizing properties, methods, or events on the bridge produced via the Execute method may indeed produce side effecting results. 


## -parameters

### -param client
An interface to the client requesting the execution should be passed here. If there are errors or other events during execution of the script, the client should be notified of those and their location within the script via methods on this interface.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDataModelScript interface](nn-dbgmodel-idatamodelscript.md)
