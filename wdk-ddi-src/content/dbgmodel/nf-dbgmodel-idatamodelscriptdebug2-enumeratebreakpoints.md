---
UID: NF:dbgmodel.IDataModelScriptDebug2.EnumerateBreakpoints
title: IDataModelScriptDebug2::EnumerateBreakpoints
author: windows-driver-content
description: TBD
ms.assetid: 32ebb52c-74b2-4966-bdb4-47c69850b18a
ms.author: windowsdriverdev
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug2::EnumerateBreakpoints, EnumerateBreakpoints, IDataModelScriptDebug2.EnumerateBreakpoints, IDataModelScriptDebug2::EnumerateBreakpoints, IDataModelScriptDebug2.EnumerateBreakpoints
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
-	IDataModelScriptDebug2.EnumerateBreakpoints
product: Windows
targetos: Windows


---

# IDataModelScriptDebug2::EnumerateBreakpoints


## -description
The EnumerateBreakpoints method returns an enumerator capable of enumerating every breakpoint which is set within a particular script. 

As long as the script debugger is enabled via a call to the StartDebugging method, it is legal to call this method. 


## -parameters

### -param breakpointEnum
An enumerator which enumerates every breakpoint which is set within the script (whether enabled or disabled) must be returned here.

## -returns
This method returns HRESULT.

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)
