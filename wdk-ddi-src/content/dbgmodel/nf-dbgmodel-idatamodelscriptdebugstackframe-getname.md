---
UID: NF:dbgmodel.IDataModelScriptDebugStackFrame.GetName
title: IDataModelScriptDebugStackFrame::GetName (dbgmodel.h)
description: The GetName method returns the display name (that is the function name) of this frame. Such name will be displayed within the stack backtrace presented to the user in the debugger interface.
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugStackFrame::GetName"]
ms.keywords: IDataModelScriptDebugStackFrame::GetName, GetName, IDataModelScriptDebugStackFrame.GetName, IDataModelScriptDebugStackFrame::GetName, IDataModelScriptDebugStackFrame.GetName
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
 - IDataModelScriptDebugStackFrame::GetName
 - dbgmodel/IDataModelScriptDebugStackFrame::GetName
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugStackFrame::GetName
---

# IDataModelScriptDebugStackFrame::GetName


## -description

The GetName method returns the display name (e.g.: function name) of this frame. Such name will be displayed within the stack backtrace presented to the user in the debugger interface.

## -parameters

### -param name

The display name (e.g.: function name) of the frame is returned here as a string allocated via the SysAllocString method. The caller is responsible for freeing this string with SysFreeString.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebugStackFrame interface](nn-dbgmodel-idatamodelscriptdebugstackframe.md)

