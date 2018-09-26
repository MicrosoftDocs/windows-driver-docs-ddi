---
UID: NF:dbgmodel.IDataModelScriptDebug2.StopDebugging
title: IDataModelScriptDebug2::StopDebugging
author: windows-driver-content
description: TBD
ms.assetid: 30fb6af7-b5e6-41cc-ba27-ea9ed2182541
ms.author: windowsdriverdev
ms.date: 08/21/2018 
ms.topic: method
ms.keywords: IDataModelScriptDebug2::StopDebugging, StopDebugging, IDataModelScriptDebug2.StopDebugging, IDataModelScriptDebug2::StopDebugging, IDataModelScriptDebug2.StopDebugging
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
-	IDataModelScriptDebug2.StopDebugging
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelScriptDebug2::StopDebugging


## -description


The StopDebugging method is called by a client that wants to stop debugging. This method call may be made at any point after StartDebugging was made successfully (e.g.: during a break, while the script is executing, etc...). The call immediately ceases all debugging activity and resets the state back to before StartDebugging was called. 

## -parameters

### -param debugClient

The debug client which is stopping debugging. This should match the debug client passed to the StartDebugging call. A non-matching client is an illegal call.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)
