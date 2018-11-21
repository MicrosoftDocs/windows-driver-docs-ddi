---
UID: NF:dbgmodel.IDataModelScriptDebugStackFrame.IsTransitionPoint
title: IDataModelScriptDebugStackFrame::IsTransitionPoint
author: windows-driver-content
description: The IDataModelScriptDebugStack interface represents a segment of a call stack -- that portion of the call stack which is contained within the context of one script. 
ms.assetid: 1414b5f1-bd95-46aa-90c8-efd89b75504a
ms.date: 09/10/2018
ms.topic: method
ms.keywords: IDataModelScriptDebugStackFrame::IsTransitionPoint, IsTransitionPoint, IDataModelScriptDebugStackFrame.IsTransitionPoint, IDataModelScriptDebugStackFrame::IsTransitionPoint, IDataModelScriptDebugStackFrame.IsTransitionPoint
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
-	IDataModelScriptDebugStackFrame.IsTransitionPoint
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStackFrame::IsTransitionPoint


## -description

The IDataModelScriptDebugStack interface represents a segment of a call stack -- that portion of the call stack which is contained within the context of one script. If the debugger is capable of detecting the transition from one script to another (or one script provider to another), it can indicate this by implementing the IsTransitionPoint method and returning true or false as appropriate. The call stack frame which entered the script where the segment applies should be considered a transition point. All other frames are not. 

It is perfectly legal for any script debugger which is incapable of doing cross-script debugging or detection to simply return E_NOTIMPL from this method. In such cases, the debug interface may only be able to show a stack backtrace for the current script even if the overall call stack spans multiple scripts. 


## -parameters

### -param isTransitionPoint
If this stack frame is the first frame which entered a particular script or script provider, it should return true here indicating that the frame is a transition point from one script/provider to another. For any other stack frame, false should be returned.


## -returns
This method returns HRESULT which indicates success or failure. Debuggers which are incapable of detecting transition points may return E_NOTIMPL from this method.

## -remarks

## -see-also

[IDataModelScriptDebugStackFrame interface](nn-dbgmodel-idatamodelscriptdebugstackframe.md)
