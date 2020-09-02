---
UID: NF:dbgmodel.IDataModelScriptProvider.GetExtension
title: IDataModelScriptProvider::GetExtension (dbgmodel.h)
description: The GetExtension method returns the file extension for scripts managed by this provider (without the dot) as a string allocated via the SysAllocString method.
ms.assetid: e9f079fa-3ce1-4a05-a46e-f5b5268d2a6f
ms.date: 08/20/2018
keywords: ["IDataModelScriptProvider::GetExtension"]
ms.keywords: IDataModelScriptProvider::GetExtension, GetExtension, IDataModelScriptProvider.GetExtension, IDataModelScriptProvider::GetExtension, IDataModelScriptProvider.GetExtension
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptProvider::GetExtension
 - dbgmodel/IDataModelScriptProvider::GetExtension
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptProvider.GetExtension
---

# IDataModelScriptProvider::GetExtension


## -description

The GetExtension method returns the file extension for scripts managed by this provider (without the dot) as a string allocated via the SysAllocString method. The debugger application hosting the data model (with scripting support) will delegate opening of script files with this extension to the script provider. The caller is responsible for freeing the returned string via SysFreeString. Examples of strings which might be returned from this method are "js" or "NatVis". 

No two script providers may return the same file extension (case insensitive). A provider which wishes to handle multiple file extensions must implement multiple [IDataModelScriptProvider](nn-dbgmodel-idatamodelscriptprovider.md) interfaces and provide unique names and file extensions to the script manager via the implementation of these methods.

## -parameters

### -param extension

The file extension of script files which managed by this provider is returned here. The string is allocated via SysAllocString and the caller is responsible for freeing it via SysFreeString.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptProvider interface](nn-dbgmodel-idatamodelscriptprovider.md)

