---
UID: NF:dbgmodel.IDataModelScriptDebug.StopDebugging
title: IDataModelScriptDebug::StopDebugging (dbgmodel.h)
description: The StopDebugging method is called by a client that wants to stop debugging.
ms.assetid: 92a0f999-c123-4130-afcd-581deae19647
ms.date: 08/21/2018
keywords: ["IDataModelScriptDebug::StopDebugging"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug.StopDebugging"
ms.keywords: IDataModelScriptDebug::StopDebugging, StopDebugging, IDataModelScriptDebug.StopDebugging, IDataModelScriptDebug::StopDebugging, IDataModelScriptDebug.StopDebugging
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
- IDataModelScriptDebug.StopDebugging
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug::StopDebugging


## -description

The StopDebugging method is called by a client that wants to stop debugging. This method call may be made at any point after StartDebugging was made successfully (e.g.: during a break, while the script is executing, etc...). The call immediately ceases all debugging activity and resets the state back to before StartDebugging was called. 

## -parameters

### -param debugClient

The debug client which is stopping debugging. This should match the debug client passed to the StartDebugging call. A non-matching client is an illegal call.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
