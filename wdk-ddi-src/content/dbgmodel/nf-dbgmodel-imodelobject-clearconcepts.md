---
UID: NF:dbgmodel.IModelObject.ClearConcepts
title: IModelObject::ClearConcepts (dbgmodel.h)
description: The ClearConcepts method will remove all concepts from the instance of the object specified by this. 
ms.assetid: e9b09cff-5f1d-4bcb-bd73-efaeafd91206
ms.date: 07/20/2018
keywords: ["IModelObject::ClearConcepts"]
f1_keywords:
 - "dbgmodel/IModelObject.ClearConcepts"
 - "IModelObject.ClearConcepts"
ms.keywords: IModelObject::ClearConcepts, ClearConcepts, IModelObject.ClearConcepts, IModelObject::ClearConcepts, IModelObject.ClearConcepts
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
- IModelObject.ClearConcepts
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::ClearConcepts


## -description

The ClearConcepts method will remove all concepts from the instance of the object specified by this. 

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

if (SUCCEEDED(spObject->ClearConcepts()))
{
    // All concepts are gone from spObject.  Parent models may still have concepts.  
    // GetConcept may find concepts from parent models.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)

