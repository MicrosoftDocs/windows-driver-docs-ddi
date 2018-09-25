---
UID: NF:dbgmodel.IDataModelManager2.UnregisterNamedModel
title: IDataModelManager2::UnregisterNamedModel
author: windows-driver-content
description: TBD
ms.assetid: 0bdd2601-f489-4b9d-9b9f-41f058044dc8
ms.author: windowsdriverdev
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelManager2::UnregisterNamedModel, UnregisterNamedModel, IDataModelManager2.UnregisterNamedModel, IDataModelManager2::UnregisterNamedModel, IDataModelManager2.UnregisterNamedModel
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
-	IDataModelManager2.UnregisterNamedModel
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelManager2::UnregisterNamedModel


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

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
