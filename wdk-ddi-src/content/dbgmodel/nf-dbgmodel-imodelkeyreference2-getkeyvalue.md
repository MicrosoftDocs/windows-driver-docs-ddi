---
UID: NF:dbgmodel.IModelKeyReference2.GetKeyValue
title: IModelKeyReference2::GetKeyValue (dbgmodel.h)
description: The GetKeyValue method on a key reference behaves as the GetKeyValue method on IModelObject would.
ms.assetid: f47db938-1cf3-4f6e-af51-a6e650610e7d
ms.date: 08/14/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IModelKeyReference2.GetKeyValue"
ms.keywords: IModelKeyReference2::GetKeyValue, GetKeyValue, IModelKeyReference2.GetKeyValue, IModelKeyReference2::GetKeyValue, IModelKeyReference2.GetKeyValue
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
- IModelKeyReference2.GetKeyValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelKeyReference2::GetKeyValue


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

[IModelKeyReference2 interface](nn-dbgmodel-imodelkeyreference2.md)
