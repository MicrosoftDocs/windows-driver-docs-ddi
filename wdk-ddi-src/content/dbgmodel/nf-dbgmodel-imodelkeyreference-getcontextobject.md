---
UID: NF:dbgmodel.IModelKeyReference.GetContextObject
title: IModelKeyReference::GetContextObject (dbgmodel.h)
description: "The IModelKeyReference::GetContextObject method, when called on a key reference for an object, gets the context of the object."
ms.date: 08/14/2018
keywords: ["IModelKeyReference::GetContextObject"]
ms.keywords: IModelKeyReference::GetContextObject, GetContextObject, IModelKeyReference.GetContextObject, IModelKeyReference::GetContextObject, IModelKeyReference.GetContextObject
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IModelKeyReference::GetContextObject
 - dbgmodel/IModelKeyReference::GetContextObject
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelKeyReference::GetContextObject
---

# IModelKeyReference::GetContextObject


## -description

The GetContextObject method returns the context (this pointer) which will be passed to a property accessor's GetValue or SetValue method if the key in question refers to a property accessor. The context object returned here may or may not be the same as the original object fetched from GetOriginalObject. If a key is on a parent model and there is a context adjustor associated with that parent model, the original object is the instance object on which GetKeyReference or EnumerateKeyReferences was called. The context object would be whatever comes out of the final context adjustor between the original object and the parent model containing the key to which this key reference is a handle. If there are no context adjustors, the original object and the context object are identical.

## -parameters

### -param containingObject

The context object which will be passed to any property accessor method is returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    ComPtr<IModelObject> spContextObject;
    if (SUCCEEDED(spKeyRef->GetContextObject(&spContextObject)))
    {
        // spObject and spContextObject should be the same.
        // This is *NOT* true if there was an intervening call to OverrideContextObject 
    }
}
```

## -see-also

[IModelKeyReference interface](nn-dbgmodel-imodelkeyreference.md)

