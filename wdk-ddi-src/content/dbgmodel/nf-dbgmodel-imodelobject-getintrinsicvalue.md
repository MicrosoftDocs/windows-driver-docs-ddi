---
UID: NF:dbgmodel.IModelObject.GetIntrinsicValue
title: IModelObject::GetIntrinsicValue
author: windows-driver-content
description: TBD
ms.assetid: 95a2f002-c6d9-48c2-9c7f-86df732a0584
ms.author: windowsdriverdev
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetIntrinsicValue, GetIntrinsicValue, IModelObject.GetIntrinsicValue, IModelObject::GetIntrinsicValue, IModelObject.GetIntrinsicValue
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
-	IModelObject.GetIntrinsicValue
product: Windows
targetos: Windows


tech.root: debugger
---

# IModelObject::GetIntrinsicValue


## -description

The GetIntrinsicValue method returns the thing which is boxed inside an IModelObject. This method may only legally be called on IModelObject interfaces which represent a boxed intrinsic or a particular interface which is boxed. It cannot be called on native objects, no value objects, synthetic objects, and reference objects. 

## -parameters

### -param intrinsicData

The value boxed inside the IModelObject is returned here. The pointer must point to a VARIANT structure which does not contain a freeable value. It is the responsibility of the caller to clear this VARIANT with VariantClear when finished with it.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get something */

VARIANT vtVal;
HRESULT hr = spObject->GetIntrinsicValue(&vtVal);
if (SUCCEEDED(hr) && vtVal.vt == VT_I4)
{
    int iVal = vtVal.lVal; // An integer has been unboxed into iVal.
}
VariantClear(&vtVal);
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
