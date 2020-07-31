---
UID: NF:dbgmodel.IDataModelManager.UnregisterExtensionForTypeSignature
title: IDataModelManager::UnregisterExtensionForTypeSignature (dbgmodel.h)
description: The UnregisterExtensionForTypeSignature method undoes a prior call to RegisterExtensionForTypeSignature.
ms.assetid: b3761aea-406a-4446-8467-31dd1a7b742c
ms.date: 07/19/2018
keywords: ["IDataModelManager::UnregisterExtensionForTypeSignature"]
f1_keywords:
 - "dbgmodel/IDataModelManager.UnregisterExtensionForTypeSignature"
 - "IDataModelManager.UnregisterExtensionForTypeSignature"
ms.keywords: IDataModelManager::UnregisterExtensionForTypeSignature, UnregisterExtensionForTypeSignature, IDataModelManager.UnregisterExtensionForTypeSignature, IDataModelManager::UnregisterExtensionForTypeSignature, IDataModelManager.UnregisterExtensionForTypeSignature
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
- IDataModelManager.UnregisterExtensionForTypeSignature
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::UnregisterExtensionForTypeSignature


## -description

The UnregisterExtensionForTypeSignature method undoes a prior call to RegisterExtensionForTypeSignature. It unregisters a particular data model as an extension for either a particular type signature or as an extension for all type signatures against which the data model was registered. 

## -parameters

### -param dataModel
The data model to unregister as an extension from one or more type signatures. If a specific type signature is passed in the typeSignature argument, this data model will be unregistered as an extension from that particular type signature. Newly created native/language objects with concrete types which match the signature will no longer have this data model automatically attached. If typeSignature is passed as nullptr, this data model will be unregistered from every type signature that it was registered against.

### -param typeSignature
The type signature from which dataModel should be unregistered as an extension. If this argument is nullptr, the data model given by the dataModel argument will be unregistered as an extension from every type signature it was registered against.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager;             /* get the data model manager */
ComPtr<IDebugHostTypeSignature> spTypeSignature; /* get a type signature (see 
                                                  RegisterExtensionForTypeSignature) */
ComPtr<IModelObject> spDataModelObject;          /* get a data model object (see
                                                    CreateDataModelObject) */

if (SUCCEEDED(spManager->UnregisterExtensionForTypeSignature(spDataModelObject.Get(),
                                                             spTypeSignature.Get())))
{
    // spDataModelObject is no longer registered as an extension for types 
    // matching the signature.  Note that if the second argument were passed
    // as 'nullptr', spDataModelObject would no longer be registered as an
    // extension for *ANY* types.
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
