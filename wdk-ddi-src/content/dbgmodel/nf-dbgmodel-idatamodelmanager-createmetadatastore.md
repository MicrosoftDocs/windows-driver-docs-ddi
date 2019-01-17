---
UID: NF:dbgmodel.IDataModelManager.CreateMetadataStore
title: IDataModelManager::CreateMetadataStore
description: The CreateMetadataStore method creates a key store which is used to hold metadata that can be associated with properties and a variety of other values.
ms.assetid: e2b707f0-3901-4bf4-8f47-68ab79f6999b
ms.date: 07/20/2018
ms.topic: method
ms.keywords: IDataModelManager::CreateMetadataStore, CreateMetadataStore, IDataModelManager.CreateMetadataStore, IDataModelManager::CreateMetadataStore, IDataModelManager.CreateMetadataStore
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
-	IDataModelManager.CreateMetadataStore
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::CreateMetadataStore


## -description

The CreateMetadataStore method creates a key store -- a simplified container of key/value/metadata tuples -- which is used to hold metadata that can be associated with properties and a variety of other values. 

A metadata store may have a single parent (which in turn can have a single parent). If a given metadata key is not located in a given store, its parents are checked. Most metadata stores do not have parents. It does, however, provide a way of sharing common metadata easily. 


## -parameters

### -param parentStore
The parent store for the newly created metadata store. This may be null if there is no parent.

### -param metadataStore
The newly created metadata store will be returned here.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

// Create an empty key store (the usual case) which will be later filled with metadata.
ComPtr<IKeyStore> spMetadata;
if (SUCCEEDED(spManager->CreateMetadataStore(nullptr, &spMetadata)))
{
    // spMetadata now is an empty store.  You can set key values 
    // like 'PreferredRadix', 'PreferredFormat', 'PreferredLength', etc...
    ComPtr<IKeyStore> spChildMetadata;
    if (SUCCEEDED(spManager->CreateMetadataStore(spMetadata.Get(), &spChildMetadata)))
    {
        // spChildMetadata now is an empty store.  If a key queried from 
        // it does not exist there, it will be queried from spMetadata.
        // This can be useful to override properties on some store without
        // modifying or copying it.
    }
}
```



## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
