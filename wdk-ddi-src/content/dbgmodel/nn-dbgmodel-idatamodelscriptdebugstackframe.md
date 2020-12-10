---
UID: NN:dbgmodel.IDataModelScriptDebugStackFrame
title: IDataModelScriptDebugStackFrame (dbgmodel.h)
description: An interface to a stack frame in the script. The script provider implements this interface to expose the notion of a particular stack frame within the call stack.
ms.date: 07/13/2018
keywords: ["IDataModelScriptDebugStackFrame interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
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
 - IDataModelScriptDebugStackFrame
 - dbgmodel/IDataModelScriptDebugStackFrame
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugStackFrame
---

# IDataModelScriptDebugStackFrame interface


## -description

An interface to a stack frame in the script.

The script provider implements this interface to expose the notion of a particular stack frame within the call stack.

## -inheritance

IDataModelScriptDebugStackFrame interits from IUnknown.

## -remarks

A particular frame of the call stack when broken into the script debugger can be retrieved via a call to the GetStackFrame method on the [IDataModelScriptDebugStack](nn-dbgmodel-idatamodelscriptdebugstack.md) interface representing the stack segment where the break occurred. The IDataModelScriptDebugStackFrame interface which is returned to represent this frame.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
