---
UID: NF:dbgmodel.IModelKeyReference.GetOriginalObject
title: IModelKeyReference::GetOriginalObject (dbgmodel.h)
description: The GetOriginalObject method returns the instance object from which the key reference was created.
ms.assetid: 90470310-3ddb-444d-bf70-835cf42ea2ae
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IModelKeyReference::GetOriginalObject, GetOriginalObject, IModelKeyReference.GetOriginalObject, IModelKeyReference::GetOriginalObject, IModelKeyReference.GetOriginalObject
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
-	IModelKeyReference.GetOriginalObject
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelKeyReference::GetOriginalObject


## -description

The GetOriginalObject method returns the instance object from which the key reference was created. Note that the key may itself be on a parent model of the instance object. 

## -parameters

### -param originalObject
The instance object from which the key reference was created will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    ComPtr<IModelObject> spOriginalObject;
    if (SUCCEEDED(spKeyRef->GetOriginalObject(&spOriginalObject)))
    {
        // spObject and spOriginalObject should be the same.
        // This is true even if someone calls
        // IModelKeyReference2::OverrideContextObject with some other object.
    }
}
```

## -see-also

[IModelKeyReference interface](nn-dbgmodel-imodelkeyreference.md)
