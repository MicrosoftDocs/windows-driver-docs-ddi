---
UID: NF:dbgmodel.IKeyStore.SetKeyValue
title: IKeyStore::SetKeyValue (dbgmodel.h)
description: The SetKeyValue method is analogous to the SetKeyValue method on IModelObject.
ms.assetid: 335a6361-3c79-4eb7-96e0-ca54098ba607
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IKeyStore::SetKeyValue, SetKeyValue, IKeyStore.SetKeyValue, IKeyStore::SetKeyValue, IKeyStore.SetKeyValue
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
- IKeyStore.SetKeyValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IKeyStore::SetKeyValue


## -description

The SetKeyValue method is analogous to the SetKeyValue method on IModelObject. This method is not capable of creating a new key within the metadata store. If there is an existing key as indicated by the key argument, its value will be set as indicated. If the key is a property accessor, the SetValue method will be called on the property accessor in order to set the underlying value. Note that metadata is typically static once created. Use of this method on a metadata key store should be infrequent. 

## -parameters

### -param key
The name of the key to set a value for.

### -param object
The value to assign to the key. If the current key's value is a property accessor, the SetValue method will be called on the property accessor to set the underlying value.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IKeyStore> spMetadata; /* get a metadata store */
ComPtr<IModelObject> spValue; /* get a value to set */

// This never creates a key.  Most callers should prefer SetKey
if (SUCCEEDED(spMetadata->SetKeyValue(L"KnownExistingKey", spValue.Get()))
{
    // The key's value was successfully set.
}
```

## -see-also

[IKeyStore interface](nn-dbgmodel-ikeystore.md)
