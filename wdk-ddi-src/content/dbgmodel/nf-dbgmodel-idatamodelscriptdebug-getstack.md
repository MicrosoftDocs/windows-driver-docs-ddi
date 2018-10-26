---
UID: NF:dbgmodel.IDataModelScriptDebug.GetStack
title: IDataModelScriptDebug::GetStack
author: windows-driver-content
description: The GetStack method gets the current call stack at the break position.
ms.assetid: 7de93afc-3f25-45be-9733-e6cd3c87ed00
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug::GetStack, GetStack, IDataModelScriptDebug.GetStack, IDataModelScriptDebug::GetStack, IDataModelScriptDebug.GetStack
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
-	IDataModelScriptDebug.GetStack
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptDebug::GetStack


## -description

The GetStack method gets the current call stack at the break position. This method may only be called when the script is broken into the debugger. 

## -parameters

### -param stack

A component implementing IDataModelScriptDebugStack is returned here representing the call stack state at the position of the break.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
