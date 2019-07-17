---
UID: NF:dbgmodel.IDataModelManager2.CreateMetadataStore
title: IDataModelManager2::CreateMetadataStore (dbgmodel.h)
description: The CreateMetadataStore method creates a key store which is used to hold metadata that can be associated with properties and a variety of other values.
ms.assetid: 545fd9fa-22bf-4bdd-b898-d5533fe8df81
ms.date: 09/11/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDataModelManager2.CreateMetadataStore"
ms.keywords: IDataModelManager2::CreateMetadataStore, CreateMetadataStore, IDataModelManager2.CreateMetadataStore, IDataModelManager2::CreateMetadataStore, IDataModelManager2.CreateMetadataStore
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
- IDataModelManager2.CreateMetadataStore
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager2::CreateMetadataStore


## -description

The CreateMetadataStore method creates a key store -- a simplified container of key/value/metadata tuples -- which is used to hold metadata that can be associated with properties and a variety of other values. 

A metadata store may have a single parent (which in turn can have a single parent). If a given metadata key is not located in a given store, its parents are checked. Most metadata stores do not have parents. It does, however, provide a way of sharing common metadata easily. 


## -parameters

### -param parentStore
The parent store for the newly created metadata store. This may be null if there is no parent.


### -param metadataStore
The newly created metadata store will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

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

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
