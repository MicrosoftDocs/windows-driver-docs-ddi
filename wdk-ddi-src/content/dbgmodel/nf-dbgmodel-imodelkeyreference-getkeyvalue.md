---
UID: NF:dbgmodel.IModelKeyReference.GetKeyValue
title: IModelKeyReference::GetKeyValue (dbgmodel.h)
description: "The IModelKeyReference::GetKeyValue method, when called on a key reference, gets the value of the underlying key and any metadata associated with it."
ms.date: 08/14/2018
keywords: ["IModelKeyReference::GetKeyValue"]
ms.keywords: IModelKeyReference::GetKeyValue, GetKeyValue, IModelKeyReference.GetKeyValue, IModelKeyReference::GetKeyValue, IModelKeyReference.GetKeyValue
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
 - IModelKeyReference::GetKeyValue
 - dbgmodel/IModelKeyReference::GetKeyValue
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelKeyReference::GetKeyValue
---

# IModelKeyReference::GetKeyValue


## -description

The GetKeyValue method on a key reference behaves as the GetKeyValue method on [IModelObject](nn-dbgmodel-imodelobject.md) would. It returns the value of the underlying key and any metadata associated with the key. If the value of the key happens to be a property accessor, this will call the underlying GetValue method on the property accessor automatically.

## -parameters

### -param object

The value of the key will be returned here. Note that extended error information may be returned here on failure.

### -param metadata

Optional metadata which is associated with the key will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    ComPtr<IModelObject> spId;
    if (SUCCEEDED(spKeyRef->GetKeyValue(&spId, nullptr)))
    {
        // spId contains the value of the "Id" key
    }
}
```

## -see-also

[IModelKeyReference interface](nn-dbgmodel-imodelkeyreference.md)

