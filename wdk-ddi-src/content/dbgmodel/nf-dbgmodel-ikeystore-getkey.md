---
UID: NF:dbgmodel.IKeyStore.GetKey
title: IKeyStore::GetKey (dbgmodel.h)
description: The GetKey method is analogous to the GetKey method on IModelObject.
ms.assetid: 9a27d20b-76ff-4b7c-8782-95bd6288e592
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IKeyStore::GetKey, GetKey, IKeyStore.GetKey, IKeyStore::GetKey, IKeyStore.GetKey
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
-	IKeyStore.GetKey
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IKeyStore::GetKey


## -description

The GetKey method is analogous to the GetKey method on IModelObject. It will return the value of the specified key if it exists in the key store or the key store's parent store. Note that if the value of the key is a property accessor, the GetValue method will not be called on the property accessor. The actual IModelPropertyAccessor boxed into an IModelObject will be returned. It is typical that a client will call GetKeyValue for this reason. 

## -parameters

### -param key
The name of the key to get a value for

### -param object
The value of the key will be returned in this argument.

### -param metadata
The metadata store associated with this key will be optionally returned in this argument. There is no present use for second level metadata. This argument should therefore typically be specified as null.


## -returns
This method returns HRESULT that indicates success or failure. The return values E_BOUNDS (or E_NOT_SET in some cases) indicates the key could not be found.

## -remarks
**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */
ComPtr<IKeyStore> spMetadata;  /* get a key store from spObject (say 
                                  returned from GetKeyValue) */

ComPtr<IModelObject> spRadixKey;
if (SUCCEEDED(spMetadata->GetKey(L"PreferredRadix", &spRadixKey, nullptr)))
{
    // Since this is GetKey and not GetKeyValue, spRadixKey *MAY* be a 
    // property accessor.  Check and fetch.
    ModelObjectKind kind;
    if (SUCCEEDED(spRadixKey->GetKind(&kind)))
    {
        if (kind == ObjectPropertyAccessor)
        {
            VARIANT vtProp;
            if (SUCCEEDED(spRadixKey->GetIntrinsicValue(&vtProp)))
            {
                // There is a guarantee in-process that the IUnknown here 
                // is IModelPropertyAccessor because of the ObjectPropertyAccessor.
                IModelPropertyAccessor *pProperty = 
                    static_cast<IModelPropertyAccessor *>(vtProp.punkVal);
                
                ComPtr<IModelObject> spRadix; 

                // It is important that the context object be the object where 
                // the metadata store CAME FROM.  Hence the second argument
                // of spObject.Get().  Note that if you use GetKeyValue on the store,
                // this is automatically handled for you.
                if (SUCCEEDEDED(pProperty->GetValue(L"PreferredRadix", 
                                                    spObject.Get(), 
                                                    &spRadix)))
                {
                    // spRadix has the radix.  Use GetIntrinsicValueAs to unbox.
                }
                VariantClear(&vtProp);
            }
        }
        else
        {
            // spRadixKey has the radix.  Use GetIntrinsicValueAs to unbox.
        }
    }
}
```

## -see-also

[IKeyStore interface](nn-dbgmodel-ikeystore.md)
