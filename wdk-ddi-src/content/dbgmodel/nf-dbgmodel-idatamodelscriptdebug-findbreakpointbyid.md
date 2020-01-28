---
UID: NF:dbgmodel.IDataModelScriptDebug.FindBreakpointById
title: IDataModelScriptDebug::FindBreakpointById (dbgmodel.h)
description: Each breakpoint which is created within the script via the SetBreakpoint method is assigned a unique identifier (a 64-bit unsigned integer) by the implementation.
ms.assetid: 138bcb48-3c97-4633-9922-75d37e774027
ms.date: 08/21/2018
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug.FindBreakpointById"
ms.keywords: IDataModelScriptDebug::FindBreakpointById, FindBreakpointById, IDataModelScriptDebug.FindBreakpointById, IDataModelScriptDebug::FindBreakpointById, IDataModelScriptDebug.FindBreakpointById
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
- IDataModelScriptDebug.FindBreakpointById
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug::FindBreakpointById


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

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
