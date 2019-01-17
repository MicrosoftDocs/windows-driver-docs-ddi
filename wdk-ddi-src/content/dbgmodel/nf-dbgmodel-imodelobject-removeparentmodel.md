---
UID: NF:dbgmodel.IModelObject.RemoveParentModel
title: IModelObject::RemoveParentModel
description: The RemoveParentModel will remove a specified parent model from the parent search chain of the given object.
ms.assetid: 2a3fb86c-b9f4-4275-82e6-c6ff24f2fc4c
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelObject::RemoveParentModel, RemoveParentModel, IModelObject.RemoveParentModel, IModelObject::RemoveParentModel, IModelObject.RemoveParentModel
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
-	IModelObject.RemoveParentModel
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::RemoveParentModel


## -description

The RemoveParentModel will remove a specified parent model from the parent search chain of the given object. 

## -parameters

### -param model
The parent model to remove from this object.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject;          /* get an object */
ComPtr<IModelObject> spDataModelObject; /* get an attached data model (from earlier add or from GetParentModel) */

if (SUCCEEDED(spObject->RemoveParentModel(spDataModelObject.Get())))
{
    // spObject no longer has the properties or concepts exposed by spDataModelObject
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
