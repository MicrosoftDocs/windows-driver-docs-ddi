---
UID: NF:dbgmodel.IDataModelScriptProvider.EnumerateTemplates
title: IDataModelScriptProvider::EnumerateTemplates (dbgmodel.h)
description: The EnumerateTemplates method returns an enumerator which is capable of enumerating the variety of templates that are provided by the script provider.
ms.assetid: 9d814794-0a1a-4de8-8f2c-3cb2f3d48b76
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScriptProvider::EnumerateTemplates, EnumerateTemplates, IDataModelScriptProvider.EnumerateTemplates, IDataModelScriptProvider::EnumerateTemplates, IDataModelScriptProvider.EnumerateTemplates
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
- IDataModelScriptProvider.EnumerateTemplates
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptProvider::EnumerateTemplates


## -description

The EnumerateTemplates method returns an enumerator which is capable of enumerating the variety of templates that are provided by the script provider. Template content is what the script provider wants to be "prefilled" into an edit window when creating a new script. If there are multiple different templates supported, those templates can be named (e.g.: "Imperative Script", "Extension Script") and the debugger application hosting the data model can choose how to present the "templates" to the user. 

A script provider which has no template content may return E_NOTIMPL here. 


## -parameters

### -param enumerator

An enumerator which enumerates all template content of the script provider must be returned here as a component implementing the [IDataModelScriptTemplateEnumerator](nn-dbgmodel-idatamodelscripttemplateenumerator.md) interface.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptProvider interface](nn-dbgmodel-idatamodelscriptprovider.md)
