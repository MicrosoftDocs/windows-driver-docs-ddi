---
UID: NF:dbgmodel.IModelObject.GetParentModel
title: IModelObject::GetParentModel (dbgmodel.h)
description: The GetParentModel method returns the i-th parent model in the parent model chain of the given object.
ms.assetid: 14e98994-5d68-40a2-9891-df34e3e6c93f
ms.date: 08/09/2018
keywords: ["IModelObject::GetParentModel"]
ms.keywords: IModelObject::GetParentModel, GetParentModel, IModelObject.GetParentModel, IModelObject::GetParentModel, IModelObject.GetParentModel
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
 - IModelObject::GetParentModel
 - dbgmodel/IModelObject::GetParentModel
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelObject.GetParentModel
---

# IModelObject::GetParentModel


## -description

The GetParentModel method returns the i-th parent model in the parent model chain of the given object. Parent models are searched for a property or concept in the linear order they are added or enumerated. The parent model with index i of zero is searched (hierarchically) before the parent model with index i + 1.

## -parameters

### -param i

A linear zero based index indicating which parent model in the chain to retrieve.

### -param model

An [IModelObject](nn-dbgmodel-imodelobject.md) representing the i-th parent model will be returned here.

### -param contextObject

If the parent model has an associated context adjustor, the adjusted context will be returned here. See the documentation for AddParentModel for more information about this value.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ULONG64 numModels;
if (SUCCEEDED(spObject->GetNumberOfParentModels(&numModels)))
{
    // Enumerate the set of parents in linear resolution order:
    for (ULONG64 i = 0; i < numModels; ++i)
    {
        ComPtr<IModelObject> spParent;
        ComPtr<IModelObject> spContextAdjustor;
        if (SUCCEEDED(spObject->GetParentModel(i, &spParent, &spContextAdjustor)))
        {
            // spParent contains the i-th parent model
            // spContext optionally contains a context adjustor.  Properties above 
            //     this in the tree will use this context instead of spObject.
            //     Conceptually, this is a *this* pointer thunk/adjustor.  The 
            //     adjustor can be a property which must be fetched instead of a static value.
        }
    }
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)

