---
UID: NF:dbgmodel.IDataModelScriptDebugBreakpoint.GetId
title: IDataModelScriptDebugBreakpoint::GetId (dbgmodel.h)
description: The GetId method returns the unique identifier assigned by the script provider's debug engine to the breakpoint. 
ms.assetid: bc277aed-d7ac-4bd9-b3bb-4ef27489eabc
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugBreakpoint::GetId"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugBreakpoint.GetId"
ms.keywords: IDataModelScriptDebugBreakpoint::GetId, GetId, IDataModelScriptDebugBreakpoint.GetId, IDataModelScriptDebugBreakpoint::GetId, IDataModelScriptDebugBreakpoint.GetId
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
- IDataModelScriptDebugBreakpoint.GetId
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugBreakpoint::GetId


## -description

The GetId method returns the unique identifier assigned by the script provider's debug engine to the breakpoint. This identifier must be unique within the context of the containing script. The breakpoint identifier may be unique to the provider; however, that is not required. 

## -returns
This method returns ULONG64. The value is the unique identifier assigned to the breakpoint.

## -remarks



## -see-also

[IDataModelScriptDebugBreakpoint interface](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md)
