---
UID: NF:dbgmodel.IKeyStore.SetKey
title: IKeyStore::SetKey (dbgmodel.h)
description: The SetKey method is analogous to the SetKey method on IModelObject.
ms.assetid: ad29e237-ecce-4109-9b5e-24b914ca8bb7
ms.date: 08/13/2018
keywords: ["IKeyStore::SetKey"]
f1_keywords:
 - "dbgmodel/IKeyStore.SetKey"
 - "IKeyStore.SetKey"
ms.keywords: IKeyStore::SetKey, SetKey, IKeyStore.SetKey, IKeyStore::SetKey, IKeyStore.SetKey
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
- IKeyStore.SetKey
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IKeyStore::SetKey


## -description

The SetKey method is analogous to the SetKey method on [IModelObject](nn-dbgmodel-imodelobject.md). It is the only method which is capable of creating a key and associating metadata with it within the key store. 

## -parameters

### -param key
The name of the key to create or set a value for.

### -param object
The value of the key.

### -param metadata
Optional metadata to be associated with this key. There is no present use for second level metadata. This argument should therefore typically be specified as null.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks
**Code Sample**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IKeyStore> spMetadata;        /* get or create a metadata store */

ComPtr<IModelObject> sp16;
VARIANT vt16;
vt16.vt = VT_UI4;
vt16.ulVal = 16;
if (SUCCEEDED(spManager->CreateIntrinsicObject(ObjectIntrinsic, &vt16, &sp16)))
{
    if (SUCCEEDED(spMetadata->SetKey(L"PreferredRadix", sp16.Get(), nullptr)))
    {
        // The 'PreferredRadix' key has been set to 16 (even if it did 
        // not exist).  If this metadata store is passed to something like
        // IStringDisplayableConcept::ToDisplayString, the conversion of numbers 
        // will happen in hexadecimal instead of the default radix.
    }
}
```

## -see-also

[IKeyStore interface](nn-dbgmodel-ikeystore.md)
