---
UID: NF:dbgmodel.IDataModelScriptManager.RegisterScriptProvider
title: IDataModelScriptManager::RegisterScriptProvider
author: windows-driver-content
description: The RegisterScriptProvider method informs the data model that a new script provider exists which is capable of bridging a new language to the data model.
ms.assetid: b1e9628f-51b0-41a6-a3c0-8b264f0ca490
ms.author: windowsdriverdev
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScriptManager::RegisterScriptProvider, RegisterScriptProvider, IDataModelScriptManager.RegisterScriptProvider, IDataModelScriptManager::RegisterScriptProvider, IDataModelScriptManager.RegisterScriptProvider
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
-	IDataModelScriptManager.RegisterScriptProvider
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptManager::RegisterScriptProvider


## -description

The RegisterScriptProvider method informs the data model that a new script provider exists which is capable of bridging a new language to the data model. When this method is called, the script manager will immediately call back the given script provider and inquire about the properties of the scripts it manages. If there is already a provider registered under the name or file extension which the given script provider indicates, this method will fail. Only a single script provider can be registered as the handler for a particular name or file extension. 

## -parameters

### -param provider
The script provider being registered with the script manager.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptManager interface](nn-dbgmodel-idatamodelscriptmanager.md)
