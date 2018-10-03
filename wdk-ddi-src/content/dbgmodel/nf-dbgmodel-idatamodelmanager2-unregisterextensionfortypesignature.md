---
UID: NF:dbgmodel.IDataModelManager2.UnregisterExtensionForTypeSignature
title: IDataModelManager2::UnregisterExtensionForTypeSignature
author: windows-driver-content
description: The UnregisterExtensionForTypeSignature method undoes a prior call to RegisterExtensionForTypeSignature. 
ms.assetid: a92a25e0-191c-40fb-a0bc-7d29afbbcaaa
ms.author: windowsdriverdev
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelManager2::UnregisterExtensionForTypeSignature, UnregisterExtensionForTypeSignature, IDataModelManager2.UnregisterExtensionForTypeSignature, IDataModelManager2::UnregisterExtensionForTypeSignature, IDataModelManager2.UnregisterExtensionForTypeSignature
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
-	IDataModelManager2.UnregisterExtensionForTypeSignature
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelManager2::UnregisterExtensionForTypeSignature


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
ComPtr<IDataModelManager2> spManager;             /* get the data model manager */
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

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
