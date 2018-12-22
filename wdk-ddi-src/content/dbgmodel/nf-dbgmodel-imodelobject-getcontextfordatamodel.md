---
UID: NF:dbgmodel.IModelObject.GetContextForDataModel
title: IModelObject::GetContextForDataModel
description: The GetContextForDataModel method is used to retrieve context information which was set up with a prior call to SetContextForDataModel. 
ms.assetid: ee97f69a-f378-47d6-9633-3b0e5bef6451
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetContextForDataModel, GetContextForDataModel, IModelObject.GetContextForDataModel, IModelObject::GetContextForDataModel, IModelObject.GetContextForDataModel
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
-	IModelObject.GetContextForDataModel
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetContextForDataModel


## -description

The GetContextForDataModel method is used to retrieve context information which was set up with a prior call to SetContextForDataModel. This retrieves state information which was set on an instance object by a data model further up in the instance object's parent model hierarchy. 

For more details about this context/state and its meaning, see the documentation for [SetContextForDataModel](nf-dbgmodel-imodelobject-setcontextfordatamodel.md). 


## -parameters

### -param dataModelObject

The IModelObject representing the data model for which state is being retrieved from an instance object. This is, in effect, a hash key to the associated state object.

### -param context
The state which was associated with the instance is returned here. The exact meaning of this (and any other interfaces, etc... it supports) is up to the data model that made the call to set the state.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject;          /* get an object */
ComPtr<IModelObject> spDataModelObject; /* get a data model object (from an earlier AddParentModel or from GetParentModel, etc...) */

ComPtr<IUnknown> spContext;
if (SUCCEEDED(spObject->GetContextForDataModel(spDataModelObject.Get(), &spContext)))
{
    // Whatever context was associated with spObject for spDataModelObject through a 
    // prior call to SetContextForDataModel has been fetched.  You can static_cast 
    // (in process) or query spContext for the information you need since it is 
    // private implementation.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
