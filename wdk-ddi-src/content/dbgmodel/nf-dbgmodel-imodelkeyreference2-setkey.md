---
UID: NF:dbgmodel.IModelKeyReference2.SetKey
title: IModelKeyReference2::SetKey (dbgmodel.h)
description: The SetKey method on a key reference behaves as the SetKey method on IModelObject would. 
ms.assetid: 0be584a7-9024-4b41-8957-d506b3b7b965
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IModelKeyReference2::SetKey, SetKey, IModelKeyReference2.SetKey, IModelKeyReference2::SetKey, IModelKeyReference2.SetKey
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
-	IModelKeyReference2.SetKey
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelKeyReference2::SetKey


## -description

The SetKey method on a key reference behaves as the SetKey method on IModelObject would. It will assign the value of the key. If the original key was a property accessor, this will replace the property accessor. It will not call the SetValue method on the property accessor. 

## -parameters

### -param object
The value to assign to the key.

### -param metadata
Optional metadata to be associated with the key.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IModelObject> spObject;       /* get an object */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    VARIANT vtValue;
    vtValue.vt = VT_UI8;
    vtValue.ullVal = 42;

    ComPtr<IModelObject> sp42;
    if (SUCCEEDED(spManager->CreateIntrinsicObject(ObjectIntrinsic, &vtValue, &sp42)))
    {
        if (SUCCEEDED(spKeyRef->SetKey(sp42.Get(), nullptr)))
        {
            // The "Id" key has been overwritten with the value 42.  
            // If the "Id" key originally was a property accessor, it isn't anymore.
            // This would not have called SetValue() on the property accessor.  
            // It replaced the property accessor with a static "42".
        }
    }
}
```
## -see-also

[IModelKeyReference2 interface](nn-dbgmodel-imodelkeyreference2.md)
