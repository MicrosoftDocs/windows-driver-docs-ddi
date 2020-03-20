---
UID: NF:dbgmodel.IModelObject.ClearKeys
title: IModelObject::ClearKeys (dbgmodel.h)
description: The ClearKeys method removes all keys and their associated values and metadata from the instance of the object specified by this. 
ms.assetid: 7922533c-4454-4300-943d-5a7c3cd68f22
ms.date: 07/20/2018
keywords: ["IModelObject::ClearKeys"]
f1_keywords:
 - "dbgmodel/IModelObject.ClearKeys"
ms.keywords: IModelObject::ClearKeys, ClearKeys, IModelObject.ClearKeys, IModelObject::ClearKeys, IModelObject.ClearKeys
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
- IModelObject.ClearKeys
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::ClearKeys


## -description

The ClearKeys method removes all keys and their associated values and metadata from the instance of the object specified by this. This method has no effect on parent models attached to the particular object instance. 

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

if (SUCCEEDED(spObject->ClearKeys()))
{
    // The *instance* spObject has no keys.  Parent models may still have keys.
    // EnumerateKeyValues / EnumerateKeys / etc... may still return those parent keys.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
