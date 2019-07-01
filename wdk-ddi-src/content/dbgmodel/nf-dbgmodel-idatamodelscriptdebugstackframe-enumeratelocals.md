---
UID: NF:dbgmodel.IDataModelScriptDebugStackFrame.EnumerateLocals
title: IDataModelScriptDebugStackFrame::EnumerateLocals (dbgmodel.h)
description: The EnumerateLocals method returns a variable set for all local variables which are in scope in the context of the stack frame represented by the IDataModelScriptDebugStackFrame. 
ms.assetid: c538a07f-cd0c-44a5-897a-2e35920685d5
ms.date: 09/10/2018
ms.topic: method
ms.keywords: IDataModelScriptDebugStackFrame::EnumerateLocals, EnumerateLocals, IDataModelScriptDebugStackFrame.EnumerateLocals, IDataModelScriptDebugStackFrame::EnumerateLocals, IDataModelScriptDebugStackFrame.EnumerateLocals
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
- IDataModelScriptDebugStackFrame.EnumerateLocals
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStackFrame::EnumerateLocals


## -description

The EnumerateLocals method returns a variable set (represented by an [IDataModelScriptDebugVariableSetEnumerator](nn-dbgmodel-idatamodelscriptdebugvariablesetenumerator.md) interface) for all local variables which are in scope in the context of the stack frame represented by the [IDataModelScriptDebugStackFrame](nn-dbgmodel-idatamodelscriptdebugstackframe.md) interface on which this method was called. 

Note that if there are multiple definitions of a single variable where an inner scope eclipses an outer scope, only a single definition should be returned -- the definition which is in scope at the code position represented by the frame. 


## -parameters

### -param variablesEnum
A variable set enumerator which enumerates all in-scope local variables at the code position represented by the stack frame.


## -returns
This method returns HRESULT which indicates success or failure.
## -remarks

## -see-also

[IDataModelScriptDebugStackFrame interface](nn-dbgmodel-idatamodelscriptdebugstackframe.md)
