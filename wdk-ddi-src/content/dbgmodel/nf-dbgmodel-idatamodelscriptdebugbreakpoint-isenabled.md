---
UID: NF:dbgmodel.IDataModelScriptDebugBreakpoint.IsEnabled
title: IDataModelScriptDebugBreakpoint::IsEnabled (dbgmodel.h)
description: The IsEnabled method returns whether or not the breakpoint is enabled.
ms.assetid: ff1e0637-59d8-4c5f-8d18-3e53da13d701
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugBreakpoint::IsEnabled"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugBreakpoint.IsEnabled"
 - "IDataModelScriptDebugBreakpoint.IsEnabled"
ms.keywords: IDataModelScriptDebugBreakpoint::IsEnabled, IsEnabled, IDataModelScriptDebugBreakpoint.IsEnabled, IDataModelScriptDebugBreakpoint::IsEnabled, IDataModelScriptDebugBreakpoint.IsEnabled
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
- IDataModelScriptDebugBreakpoint.IsEnabled
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugBreakpoint::IsEnabled


## -description

The IsEnabled method returns whether or not the breakpoint is enabled. A disabled breakpoint still exists and is still in the list of breakpoints for the script, it is merely "turned off" temporarily. All breakpoints should be created in the enabled state. 

## -returns
This method returns bool. The value is an indication of whether the breakpoint is enabled or not.

## -remarks

## -see-also

[IDataModelScriptDebugBreakpoint interface](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md)
