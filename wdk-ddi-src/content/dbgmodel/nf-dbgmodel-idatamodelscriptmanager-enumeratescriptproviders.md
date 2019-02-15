---
UID: NF:dbgmodel.IDataModelScriptManager.EnumerateScriptProviders
title: IDataModelScriptManager::EnumerateScriptProviders (dbgmodel.h)
description: The EnumerateScriptProviders method will return an enumerator which will enumerate every script provider that has been registered with the script manager via a prior call to the RegisterScriptProvider method. 
ms.assetid: c9712073-e247-45b5-be02-941ecb5fafce
ms.date: 08/20/2018
ms.topic: method
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
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelScriptManager.EnumerateScriptProviders
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
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
