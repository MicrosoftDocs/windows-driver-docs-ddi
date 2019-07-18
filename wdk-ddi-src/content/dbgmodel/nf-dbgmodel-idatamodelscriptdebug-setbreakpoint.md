---
UID: NF:dbgmodel.IDataModelScriptDebug.SetBreakpoint
title: IDataModelScriptDebug::SetBreakpoint (dbgmodel.h)
description: The SetBreakpoint method sets a breakpoint within the script.
ms.assetid: 2614e372-e4ec-44e6-8312-44fb5c0eaced
ms.date: 08/21/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug.SetBreakpoint"
ms.keywords: IDataModelScriptDebug::SetBreakpoint, SetBreakpoint, IDataModelScriptDebug.SetBreakpoint, IDataModelScriptDebug::SetBreakpoint, IDataModelScriptDebug.SetBreakpoint
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
- IDataModelScriptDebug.SetBreakpoint
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug::SetBreakpoint


## -description

The SetBreakpoint method sets a breakpoint within the script. Note that the implementation is free to adjust the inpassed line and column positions to move forward to an appropriate code position. The actual line and column numbers where the breakpoint was placed can be retrieved by method calls on the returned [IDataModelScriptDebugBreakpoint](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md) interface. 

Note that it is the responsibility of the implementation to "remember" all of the breakpoints which have been set and assign a unique identifier to each. That identifier must be unique within the domain of a single script. 

As long as the script debugger is enabled via a call to the StartDebugging method, it is legal to call this method. A breakpoint may be set before any execution occurs. 

## -parameters

### -param linePosition
The one based line number of the location in source code where the breakpoint is being set.

### -param columnPosition
The one based column number on the given line where the breakpoint is being set.

### -param breakpoint
An [IDataModelScriptDebugBreakpoint](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md) interface representing the newly created breakpoint is returned here.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
