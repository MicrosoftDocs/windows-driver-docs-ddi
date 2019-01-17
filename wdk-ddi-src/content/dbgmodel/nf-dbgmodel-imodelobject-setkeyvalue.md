---
UID: NF:dbgmodel.IModelObject.SetKeyValue
title: IModelObject::SetKeyValue
description: The SetKeyValue method is the first method a client will turn to in order to set the value of a key. This method cannot be used to create a new key on an object.
ms.assetid: ea5bb8e0-a226-4dd2-90e3-0fc7cebf9cd5
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelObject::SetKeyValue, SetKeyValue, IModelObject.SetKeyValue, IModelObject::SetKeyValue, IModelObject.SetKeyValue
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
-	IModelObject.SetKeyValue
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::SetKeyValue


## -description

The SetKeyValue method is the first method a client will turn to in order to set the value of a key. This method cannot be used to create a new key on an object. It will only set the value of an existing key. Note that many keys are read-only (e.g.: they are implemented by a property accessor which returns E_NOT_IMPL from it's SetValue method). This method will fail when called on a read only key. 

## -parameters

### -param key
The name of the key to set a value for.


### -param object
The value of the key will be set to the object contained in this argument.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IModelObject> spObject;       /* get an object with a key named SomeKey */

// Box (int)42:
VARIANT vtVal;
vtVal.vt = VT_I4;
vtVal.lVal = 42;

ComPtr<IModelObject> spNewObject;
if (SUCCEEDED(spManager->CreateIntrinsicObject(ObjectIntrinsic, &vtVal, &spNewObject)))
{
    // Set the value of "SomeKey" to our newly boxed 42:
    if (SUCCEEDED(spObject->SetKeyValue(L"SomeKey", spNewObject.Get()))
    {
        // The key value has been set!
    }
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
