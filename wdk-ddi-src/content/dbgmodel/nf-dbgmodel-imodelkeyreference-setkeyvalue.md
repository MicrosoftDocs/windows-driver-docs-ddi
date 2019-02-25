---
UID: NF:dbgmodel.IModelKeyReference.SetKeyValue
title: IModelKeyReference::SetKeyValue (dbgmodel.h)
description: The SetKeyValue method on a key reference behaves as the SetKeyValue method on IModelObject would.
ms.assetid: adb5bf4c-161a-4bbc-82b8-a23dcf101b55
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IModelKeyReference::SetKeyValue, SetKeyValue, IModelKeyReference.SetKeyValue, IModelKeyReference::SetKeyValue, IModelKeyReference.SetKeyValue
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
-	IModelKeyReference.SetKeyValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelKeyReference::SetKeyValue


## -description

The SetKeyValue method on a key reference behaves as the SetKeyValue method on IModelObject would. It will assign the value of the key. If the original key was a property accessor, this will call the underlying SetValue method on the property accessor rather than replacing the property accessor itself. 

## -parameters

### -param object
The value to assign to the key.

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
        if (SUCCEEDED(spKeyRef->SetKeyValue(sp42.Get())))
        {
            // The value of the "Id" key is now 42.  If the "Id" key originally 
            // was a property accessor, this successfully called
            // the SetValue() method on the property accessor.  In such a case, 
            // the property accessor was not replaced with the static 42, 
            // it was called to set the value 42.
        }
    }
}
```

## -see-also

[IModelKeyReference interface](nn-dbgmodel-imodelkeyreference.md)
