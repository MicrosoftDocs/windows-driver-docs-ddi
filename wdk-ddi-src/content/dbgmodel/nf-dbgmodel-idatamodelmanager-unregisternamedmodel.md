---
UID: NF:dbgmodel.IDataModelManager.UnregisterNamedModel
title: IDataModelManager::UnregisterNamedModel (dbgmodel.h)
description: "The IDataModelManager::UnregisterNamedModel method undoes a prior call to the RegisterNamedModel method."
ms.date: 07/19/2018
keywords: ["IDataModelManager::UnregisterNamedModel"]
ms.keywords: IDataModelManager::UnregisterNamedModel, UnregisterNamedModel, IDataModelManager.UnregisterNamedModel, IDataModelManager::UnregisterNamedModel, IDataModelManager.UnregisterNamedModel
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
 - IDataModelManager::UnregisterNamedModel
 - dbgmodel/IDataModelManager::UnregisterNamedModel
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager::UnregisterNamedModel
---

# IDataModelManager::UnregisterNamedModel


## -description

The UnregisterNamedModel method undoes a prior call to RegisterNamedModel. It removes the association between a data model and a name under which it can be looked up.

## -parameters

### -param modelName

The name which will be unregistered. Any data model registered under this name will no longer be registered.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager;    /* get the data model manager */

if (SUCCEEDED(spManager->UnregisterNamedModel(
    L"Debugger.Models.Process.PrivateProcessExtension")))
{
    // Whatever data model was registered under
    // Debugger.Models.Process.PrivateProcessExtension is no longer registered.
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)

