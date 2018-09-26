---
UID: NF:dbgmodel.IDataModelScriptDebugBreakpointEnumerator.GetNext
title: IDataModelScriptDebugBreakpointEnumerator::GetNext
author: windows-driver-content
description: TBD
ms.assetid: 6b07b694-39dc-4114-9d18-1656680b512b
ms.author: windowsdriverdev
ms.date: 09/10/2018
ms.topic: method
ms.keywords: IDataModelScriptDebugBreakpointEnumerator::GetNext, GetNext, IDataModelScriptDebugBreakpointEnumerator.GetNext, IDataModelScriptDebugBreakpointEnumerator::GetNext, IDataModelScriptDebugBreakpointEnumerator.GetNext
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
-	IDataModelScriptDebugBreakpointEnumerator.GetNext
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelScriptDebugBreakpointEnumerator::GetNext


## -description

The GetNext method moves the enumerator forward to the next breakpoint to be enumerated and returns the IDataModelScriptDebugBreakpoint interface for that breakpoint. If the enumerator has reached the end of the enumeration, it returns E_BOUNDS. Once the E_BOUNDS error has been produced, subsequent calls to the GetNext method will continue to produce E_BOUNDS unless an intervening call to the Reset method has been made. 

## -parameters

### -param breakpoint
The next enumerated breakpoint is returned here.

## -returns
This method returns HRESULT that indicates success or failure.
## -remarks

## -see-also

[IDataModelScriptDebugBreakpointEnumerator interface](nn-dbgmodel-idatamodelscriptdebugbreakpointenumerator.md)
