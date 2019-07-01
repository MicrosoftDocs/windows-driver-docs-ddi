---
UID: NF:dbgmodel.IKeyStore.GetKeyValue
title: IKeyStore::GetKeyValue (dbgmodel.h)
description: The GetKeyValue method is the first method a client will go to in order to find the value of a particular key within the metadata store.
ms.assetid: 12f6e029-4a70-410d-8019-f132bb48479d
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IKeyStore::GetKeyValue, GetKeyValue, IKeyStore.GetKeyValue, IKeyStore::GetKeyValue, IKeyStore.GetKeyValue
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
- IKeyStore.GetKeyValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IKeyStore::GetKeyValue


## -description

The GetKeyValue method is the first method a client will go to in order to find the value of a particular key within the metadata store. If the key specified by the key argument exists within the store (or it's parent store), the value of that key and any metadata associated with it will be returned. If the value of the key is a property accessor (an [IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md) boxed into an [IModelObject](nn-dbgmodel-imodelobject.md)), the GetValue method of the property accessor will automatically be called by GetKeyValue and the underlying value of the property returned. 

## -parameters

### -param key
The name of the key to return a value for.

### -param object
The value of the key will be returned here. If the key's value is a property accessor, the GetValue method will be called on the property accessor and that underlying value will be returned here..

### -param metadata
Any metadata which is associated with the key is optionally returned here. There is no present use for second level metadata. This argument should therefore typically be specified as null.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IKeyStore> spMetadata; /* get a metadata store */

ComPtr<IModelObject> spRadix;
if (SUCCEEDED(spMetadata->GetKeyValue(L"PreferredRadix", &spRadix, nullptr)))
{
    // spRadix has the preferred display radix.  Use GetIntrinsicValueAs to unbox.
}
```

## -see-also

[IKeyStore interface](nn-dbgmodel-ikeystore.md)
