---
UID: NF:dbgmodel.IDataModelScriptDebugStack.GetFrameCount
title: IDataModelScriptDebugStack::GetFrameCount (dbgmodel.h)
description: The GetFrameCount method returns the number of stack frames in this segment of the call stack.
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugStack::GetFrameCount"]
ms.keywords: IDataModelScriptDebugStack::GetFrameCount, GetFrameCount, IDataModelScriptDebugStack.GetFrameCount, IDataModelScriptDebugStack::GetFrameCount, IDataModelScriptDebugStack.GetFrameCount
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
 - IDataModelScriptDebugStack::GetFrameCount
 - dbgmodel/IDataModelScriptDebugStack::GetFrameCount
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugStack::GetFrameCount
---

# IDataModelScriptDebugStack::GetFrameCount


## -description

The GetFrameCount method returns the number of stack frames in this segment of the call stack. If the provider can detect frames in different script contexts or of different providers, it should indicate this to the caller by implementation of the IsTransitionPoint and GetTransition methods on the entry frame into this stack segment.

## -returns

This method returns ULONG64. The value is the number of stack frames in the current stack segment.

## -remarks

## -see-also

[IDataModelScriptDebugStack interface](nn-dbgmodel-idatamodelscriptdebugstack.md)

