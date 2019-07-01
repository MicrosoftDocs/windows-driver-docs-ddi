---
UID: NF:dbgmodel.IDataModelManager.RegisterNamedModel
title: IDataModelManager::RegisterNamedModel (dbgmodel.h)
description: The RegisterNamedModel method registers a given data model under a well known name so that it can be found by clients wishing to extend it.
ms.assetid: 77495094-e485-4c10-b7b6-a53c18180610
ms.date: 07/19/2018
ms.topic: method
ms.keywords: IDataModelManager::RegisterNamedModel, RegisterNamedModel, IDataModelManager.RegisterNamedModel, IDataModelManager::RegisterNamedModel, IDataModelManager.RegisterNamedModel
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
- IDataModelManager.RegisterNamedModel
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::RegisterNamedModel


## -description

The RegisterNamedModel method registers a given data model under a well known name so that it can be found by clients wishing to extend it. This is the primary purpose of the API -- to publish a data model as something which can be extended by retrieving the model registered under this well known name and adding a parent model to it. 
While the string passed in the modelName argument can be anything (it is just a name), there is a convention that it look like a dot separated namespace of the following form: 

```text
• Debugger.Models.* - Data models which pertain to the debug target.  

• DataModel.Models.* - Data models which pertain to the core data model itself. 

  o DataModel.Models.Concepts.* - Data models which pertain to concepts in the data model.
```

An example of such a name is Debugger.Models.Process. This is the name under which the debugger's notion of a process is registered. A client which extends process and itself is extensible might register its extensibility point as Debugger.Models.Process.NamedExtensionPoint where NamedExtensionPoint refers to the semantics being added to process. 

Note that if a given data model is registered under a name, the implementation of [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md) for that data model must have a GetName method which returns the name registered via calling this RegisterNamedModel method. 


## -parameters

### -param modelName
The root namespace of the data model is returned here.

### -param modeObject
The data model being registered.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager;    /* get the data model manager */
ComPtr<IModelObject> spDataModelObject; /* get your data model object (see
                                           CreateDataModelObject) */

// If the model is registered under a name (e.g.: 
// Debugger.Models.Process.PrivateProcessExtension as below), the
// IDataModelConcept::GetName method must return one of the registration 
// names (the one the extension considers "canonical").  It is legal for an 
// object to be registered under multiple names.
if (SUCCEEDED(spManager->RegisterNamedModel(
    L"Debugger.Models.Process.PrivateProcessExtension", 
    spDataModelObject.Get()))
    )
{
    // The model object spDataModelObject is now registered and can be looked up 
    // under the name "Debugger.Models.Process.PrivateProcessExtension".
    // This means others can extend it by fetching that name.
    //
    // Fetch it back as example:
    ComPtr<IModelObject> spFetchedModel;
    if (SUCCEEDED(spManager->AcquireNamedModel(
        L"Debugger.Models.Process.PrivateProcessExtension", 
        &spFetchedModel))
        )
    {
        // spFetchedModel should be the same as spDataModelObject
    }
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
