---
UID: NF:dbgmodel.IDataModelScriptDebugStackFrame.Evaluate
title: IDataModelScriptDebugStackFrame::Evaluate (dbgmodel.h)
description: The Evaluate method evaluates an expression (of the language of the script provider) in the context of the stack frame represented by the IDataModelScriptDebugStackFrame interface on which this method was called.
ms.assetid: ef36e451-1a5a-4ea0-a2cf-6af38fe6757c
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugStackFrame::Evaluate"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugStackFrame.Evaluate"
 - "IDataModelScriptDebugStackFrame.Evaluate"
ms.keywords: IDataModelScriptDebugStackFrame::Evaluate, Evaluate, IDataModelScriptDebugStackFrame.Evaluate, IDataModelScriptDebugStackFrame::Evaluate, IDataModelScriptDebugStackFrame.Evaluate
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
- IDataModelScriptDebugStackFrame.Evaluate
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStackFrame::Evaluate


## -description

The Evaluate method evaluates an expression (of the language of the script provider) in the context of the stack frame represented by the [IDataModelScriptDebugStackFrame](nn-dbgmodel-idatamodelscriptdebugstackframe.md) interface on which this method was called. The result of the expression evaluation must be marshaled out of the script provider as an [IModelObject](nn-dbgmodel-imodelobject.md). The properties and other constructs on the resulting [IModelObject](nn-dbgmodel-imodelobject.md) must all be able to be acquired while the debugger is in a break state. 

## -parameters

### -param pwszExpression
An expression (of the language of the script provider) to evaluate in the context of the stack frame represented by the [IDataModelScriptDebugStackFrame](nn-dbgmodel-idatamodelscriptdebugstackframe.md) on which this method was called.

### -param ppResult
The result of the expression evaluation. The script provider construct must be marshaled out to an [IModelObject](nn-dbgmodel-imodelobject.md) representation and all properties and constructs on that object must be able to be acquired while the debugger is in a break state.


## -returns
This method returns HRESULT which indicates success or failure.
## -remarks

## -see-also

[IDataModelScriptDebugStackFrame interface](nn-dbgmodel-idatamodelscriptdebugstackframe.md)
