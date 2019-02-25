---
UID: NF:dbgmodel.IDataModelScriptDebugStack.GetStackFrame
title: IDataModelScriptDebugStack::GetStackFrame (dbgmodel.h)
description: The GetStackFrame gets a particular stack frame from the stack segment.
ms.assetid: 95deead2-10cc-46cd-82c0-93ebf775f29b
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelScriptDebugStack::GetStackFrame, GetStackFrame, IDataModelScriptDebugStack.GetStackFrame, IDataModelScriptDebugStack::GetStackFrame, IDataModelScriptDebugStack.GetStackFrame
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
-	IDataModelScriptDebugStack.GetStackFrame
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStack::GetStackFrame


## -description

The GetStackFrame gets a particular stack frame from the stack segment. The call stack has a zero based indexing system: the current stack frame where the break event occurred is frame 0. The caller of the current method is frame 1 (and so forth). 

## -parameters

### -param frameNumber
The zero based index of the stack frame within this stack segment to retrieve. The top frame representing the current point where the debugger broke is frame 0. It's caller is frame 1 (and so forth).

### -param stackFrame
An interface to the given stack frame will be returned here.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also
[IDataModelScriptDebugStack interface](nn-dbgmodel-idatamodelscriptdebugstack.md)
