---
UID: NF:dbgmodel.IDataModelScriptDebugStackFrame.EnumerateArguments
title: IDataModelScriptDebugStackFrame::EnumerateArguments (dbgmodel.h)
description: Enumerates arguments to the function in this frame.
ms.assetid: 2e74264f-f0c4-4951-8cbd-dc63d5b32037
ms.date: 10/03/2018
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugStackFrame.EnumerateArguments"
ms.keywords: IDataModelScriptDebugStackFrame::EnumerateArguments, EnumerateArguments, IDataModelScriptDebugStackFrame.EnumerateArguments, IDataModelScriptDebugStackFrame::EnumerateArguments, IDataModelScriptDebugStackFrame.EnumerateArguments
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
- IDataModelScriptDebugStackFrame.EnumerateArguments
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStackFrame::EnumerateArguments


## -description

Enumerates arguments to the function in this frame.

The EnumerateArguments method returns a variable set (represented by an [IDataModelScriptDebugVariableSetEnumerator](nn-dbgmodel-idatamodelscriptdebugvariablesetenumerator.md) interface) for all function arguments of the function called in the stack frame represented by the [IDataModelScriptDebugStackFrame](nn-dbgmodel-idatamodelscriptdebugstackframe.md) interface on which this method was called. 

## -parameters

### -param variablesEnum
A variable set enumerator which enumerates all function arguments of the function called in the given stack frame.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebugStackFrame interface](nn-dbgmodel-idatamodelscriptdebugstackframe.md)
