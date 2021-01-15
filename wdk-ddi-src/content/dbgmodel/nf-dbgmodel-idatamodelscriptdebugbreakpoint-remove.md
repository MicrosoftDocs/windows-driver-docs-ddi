---
UID: NF:dbgmodel.IDataModelScriptDebugBreakpoint.Remove
title: IDataModelScriptDebugBreakpoint::Remove (dbgmodel.h)
description: The Remove method removes the breakpoint from its containing list. The breakpoint no longer semantically exists after this method returns.
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugBreakpoint::Remove"]
ms.keywords: IDataModelScriptDebugBreakpoint::Remove, Remove, IDataModelScriptDebugBreakpoint.Remove, IDataModelScriptDebugBreakpoint::Remove, IDataModelScriptDebugBreakpoint.Remove
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
 - IDataModelScriptDebugBreakpoint::Remove
 - dbgmodel/IDataModelScriptDebugBreakpoint::Remove
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugBreakpoint::Remove
---

# IDataModelScriptDebugBreakpoint::Remove


## -description

The Remove method removes the breakpoint from its containing list. The breakpoint no longer semantically exists after this method returns. The [IDataModelScriptDebugBreakpoint](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md) interface which represented the breakpoint is considered orphaned after the call. Nothing else can (legally) be done with it after this call other than releasing it.

## -remarks

## -see-also

[IDataModelScriptDebugBreakpoint interface](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md)

