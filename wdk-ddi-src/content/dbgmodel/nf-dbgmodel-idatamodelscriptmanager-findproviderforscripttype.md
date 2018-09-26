---
UID: NF:dbgmodel.IDataModelScriptManager.FindProviderForScriptType
title: IDataModelScriptManager::FindProviderForScriptType
author: windows-driver-content
description: TBD
ms.assetid: e71aa49e-bb3d-4faf-a455-139888ff6e55
ms.author: windowsdriverdev
ms.date: 08/20/2018 
ms.topic: method
ms.keywords: IDataModelScriptManager::FindProviderForScriptType, FindProviderForScriptType, IDataModelScriptManager.FindProviderForScriptType, IDataModelScriptManager::FindProviderForScriptType, IDataModelScriptManager.FindProviderForScriptType
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
-	IDataModelScriptManager.FindProviderForScriptType
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelScriptManager::FindProviderForScriptType


## -description

The FindProviderForScriptExtension method searches the script manager for a provider which has claims to support a given file extension as indicated by the scriptExtension argument. If one cannot be found, this method will fail; otherwise, such script provider will be returned to the caller. 

## -parameters

### -param scriptType
A string which describes the type of script being searched for (e.g.: JavaScript)

### -param provider
If a provider can be found which supports the type of script given by the scriptType argument, it will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptManager interface](nn-dbgmodel-idatamodelscriptmanager.md)
