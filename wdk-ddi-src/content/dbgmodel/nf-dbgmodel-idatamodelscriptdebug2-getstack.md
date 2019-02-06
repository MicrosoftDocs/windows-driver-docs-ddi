---
UID: NF:dbgmodel.IDataModelScriptDebug2.GetStack
title: IDataModelScriptDebug2::GetStack (dbgmodel.h)
description: The GetStack method gets the current call stack at the break position.
ms.assetid: 5f780a6c-c765-4b6f-baa9-d8367bfdbbec
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug2::GetStack, GetStack, IDataModelScriptDebug2.GetStack, IDataModelScriptDebug2::GetStack, IDataModelScriptDebug2.GetStack
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
-	IDataModelScriptDebug2.GetStack
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug2::GetStack


## -description
The GetStack method gets the current call stack at the break position. This method may only be called when the script is broken into the debugger. 

## -parameters

### -param stack

A component implementing IDataModelScriptDebugStack is returned here representing the call stack state at the position of the break.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)
