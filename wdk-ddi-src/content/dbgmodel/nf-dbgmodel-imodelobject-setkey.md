---
UID: NF:dbgmodel.IModelObject.SetKey
title: IModelObject::SetKey
author: windows-driver-content
description: The SetKey method is the method a client will turn to in order to create a key on an object (and potentially associate metadata with the created key). 
ms.assetid: 068f6bfc-403c-4f0c-a6ce-f782da26b0f4
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelObject::SetKey, SetKey, IModelObject.SetKey, IModelObject::SetKey, IModelObject.SetKey
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
-	IModelObject.SetKey
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelObject::SetKey


## -description

The SetKey method is the method a client will turn to in order to create a key on an object (and potentially associate metadata with the created key). If a given object already has a key with the given name, one of two behaviors will occur. If the key is on the instance given by this, the value of that key will be replaced as if the original key did not exist. If, on the other hand, the key is in the chain of parent data models of the instance given by this, a new key with the given name will be created on the instance given by this. This would, in effect, cause the object to have two keys of the same name (similar to a derived class shadowing a member of the same name as a base class). 

## -parameters

### -param key
The name of the key to set a value for.

### -param object
The value of the key will be set to the object contained in this argument.

### -param metadata
Optional metadata to be associated with the newly set key.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

// Create a new object with a property called "Test" with a value of 42.
ComPtr<IModelObject> spNewObject;
if (SUCCEEDED(spManager->CreateSyntheticObject(nullptr, &spNewObject)))
{
    VARIANT vtVal;
    vtVal.vt = VT_I4;
    vtVal.lVal = 42;

    ComPtr<IModelObject> sp42;
    if (SUCCEEDED(spManager->CreateIntrinsicObject(ObjectIntrinsic, &vtVal, &sp42)))
    {
        if (SUCCEEDED(spNewObject->SetKey(L"Test", sp42.Get(), nullptr)))
        {
            // We have placed a static "42" on the new object under the key "Test"
        }
    }
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
