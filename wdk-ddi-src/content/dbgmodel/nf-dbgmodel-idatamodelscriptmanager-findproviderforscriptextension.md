---
UID: NF:dbgmodel.IDataModelScriptManager.FindProviderForScriptExtension
title: IDataModelScriptManager::FindProviderForScriptExtension (dbgmodel.h)
description: The FindProviderForScriptExtension method searches the script manager for a provider which has claims to support a given file extension as indicated by the scriptExtension argument.
ms.assetid: fc3a765f-ab44-4db7-9ec8-3cbafe822687
ms.date: 08/20/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDataModelScriptManager.FindProviderForScriptExtension"
ms.keywords: IDataModelScriptManager::FindProviderForScriptExtension, FindProviderForScriptExtension, IDataModelScriptManager.FindProviderForScriptExtension, IDataModelScriptManager::FindProviderForScriptExtension, IDataModelScriptManager.FindProviderForScriptExtension
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
- IDataModelScriptManager.FindProviderForScriptExtension
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptManager::FindProviderForScriptExtension


## -description

The FindProviderForScriptExtension method searches the script manager for a provider which has claims to support a given file extension as indicated by the scriptExtension argument. If one cannot be found, this method will fail; otherwise, such script provider will be returned to the caller. 

## -parameters

### -param scriptExtension
The file extension for which to find a scriptprovider (e.g.: js).


### -param provider
If a provider can be found which handles the file extension given by the scriptExtension argument, it will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptManager interface](nn-dbgmodel-idatamodelscriptmanager.md)
