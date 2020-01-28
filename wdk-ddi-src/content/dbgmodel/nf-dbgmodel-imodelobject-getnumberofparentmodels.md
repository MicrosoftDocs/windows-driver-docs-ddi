---
UID: NF:dbgmodel.IModelObject.GetNumberOfParentModels
title: IModelObject::GetNumberOfParentModels (dbgmodel.h)
description: The GetNumberOfParentModels method returns the number of parent models which are attached to the given object instance.
ms.assetid: 3ef1b4c2-2f82-4455-a1de-c15d6fa6f0aa
ms.date: 08/09/2018
f1_keywords:
 - "dbgmodel/IModelObject.GetNumberOfParentModels"
ms.keywords: IModelObject::GetNumberOfParentModels, GetNumberOfParentModels, IModelObject.GetNumberOfParentModels, IModelObject::GetNumberOfParentModels, IModelObject.GetNumberOfParentModels
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
- IModelObject.GetNumberOfParentModels
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetNumberOfParentModels


## -description

The GetNumberOfParentModels method returns the number of parent models which are attached to the given object instance. Parent models are searched for properties depth-first in the linear ordering of the parent model chain. 

## -parameters

### -param numModels
The number of parent models of the given object is returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ULONG64 numModels;
if (SUCCEEDED(spObject->GetNumberOfParentModels(&numModels)))
{
    // numModels contains the number of immediate parent models (does not include 
    // grand-parents and further generations up).  If a key is queried on spObject and 
    // that instance does not have it, the query will be passed in turn to each of the
    // 'numModels' models which are attached to spObject.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
