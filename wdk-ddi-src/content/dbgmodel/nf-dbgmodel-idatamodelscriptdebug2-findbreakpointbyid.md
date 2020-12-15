---
UID: NF:dbgmodel.IDataModelScriptDebug2.FindBreakpointById
title: IDataModelScriptDebug2::FindBreakpointById (dbgmodel.h)
description: The FindBreakpointById method is used to get an interface to the breakpoint from a given identifier.
ms.date: 08/21/2018
keywords: ["IDataModelScriptDebug2::FindBreakpointById"]
ms.keywords: IDataModelScriptDebug2::FindBreakpointById, FindBreakpointById, IDataModelScriptDebug2.FindBreakpointById, IDataModelScriptDebug2::FindBreakpointById, IDataModelScriptDebug2.FindBreakpointById
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptDebug2::FindBreakpointById
 - dbgmodel/IDataModelScriptDebug2::FindBreakpointById
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebug2.FindBreakpointById
---

# IDataModelScriptDebug2::FindBreakpointById


## -description

Each breakpoint which is created within the script via the SetBreakpoint method is assigned a unique identifier (a 64-bit unsigned integer) by the implementation. The FindBreakpointById method is used to get an interface to the breakpoint from a given identifier. 

As long as the script debugger is enabled via a call to the StartDebugging method, it is legal to call this method.

## -parameters

### -param breakpointId

The unique id of the breakpoint being retrieved.

### -param breakpoint

An interface to the found breakpoint is returned here. If the breakpoint cannot be found, an error is returned.

## -returns

This method returns HRESULT.

## -remarks

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)

