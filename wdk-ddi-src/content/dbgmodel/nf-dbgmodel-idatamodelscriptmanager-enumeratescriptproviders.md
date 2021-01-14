---
UID: NF:dbgmodel.IDataModelScriptManager.EnumerateScriptProviders
title: IDataModelScriptManager::EnumerateScriptProviders (dbgmodel.h)
description: The EnumerateScriptProviders method will return an enumerator which will enumerate every script provider that has been registered with the script manager via a prior call to the RegisterScriptProvider method.
ms.date: 08/20/2018
keywords: ["IDataModelScriptManager::EnumerateScriptProviders"]
ms.keywords: IDataModelScriptManager::EnumerateScriptProviders, EnumerateScriptProviders, IDataModelScriptManager.EnumerateScriptProviders, IDataModelScriptManager::EnumerateScriptProviders, IDataModelScriptManager.EnumerateScriptProviders
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
 - IDataModelScriptManager::EnumerateScriptProviders
 - dbgmodel/IDataModelScriptManager::EnumerateScriptProviders
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptManager::EnumerateScriptProviders
---

# IDataModelScriptManager::EnumerateScriptProviders


## -description

The EnumerateScriptProviders method will return an enumerator which will enumerate every script provider that has been registered with the script manager via a prior call to the RegisterScriptProvider method.

## -parameters

### -param enumerator

An enumerator which will enumerate every script provider registered via a prior call to the RegisterScriptProvider method will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

The EnumerateScriptProviders method will return an enumerator of the following form: 

```cpp
DECLARE_INTERFACE_(IDataModelScriptProviderEnumerator, IUnknown)
{
    STDMETHOD(Reset)() PURE;

    STDMETHOD(GetNext)(_COM_Outptr_ IDataModelScriptProvider **provider) PURE;
}

```

## -see-also

[IDataModelScriptManager interface](nn-dbgmodel-idatamodelscriptmanager.md)

