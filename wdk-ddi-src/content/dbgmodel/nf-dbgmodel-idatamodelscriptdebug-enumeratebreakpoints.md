---
UID: NF:dbgmodel.IDataModelScriptDebug.EnumerateBreakpoints
title: IDataModelScriptDebug::EnumerateBreakpoints
author: windows-driver-content
description: The EnumerateBreakpoints method returns an enumerator capable of enumerating every breakpoint which is set within a particular script. 
ms.assetid: 9b4c5b34-ce0f-49dc-b53b-1d24e48a1c6b
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug::EnumerateBreakpoints, EnumerateBreakpoints, IDataModelScriptDebug.EnumerateBreakpoints, IDataModelScriptDebug::EnumerateBreakpoints, IDataModelScriptDebug.EnumerateBreakpoints
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
-	IDataModelScriptDebug.EnumerateBreakpoints
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug::EnumerateBreakpoints


## -description

The EnumerateBreakpoints method returns an enumerator capable of enumerating every breakpoint which is set within a particular script. 

As long as the script debugger is enabled via a call to the StartDebugging method, it is legal to call this method. 


## -parameters

### -param breakpointEnum
An enumerator which enumerates every breakpoint which is set within the script (whether enabled or disabled) must be returned here.

## -returns
This method returns HRESULT.
## -remarks

## -see-also

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
