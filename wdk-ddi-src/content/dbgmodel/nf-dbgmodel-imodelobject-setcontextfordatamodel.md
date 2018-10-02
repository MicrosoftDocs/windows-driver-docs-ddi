---
UID: NF:dbgmodel.IModelObject.SetContextForDataModel
title: IModelObject::SetContextForDataModel
author: windows-driver-content
description: TBD
ms.assetid: 717eb159-c61b-4061-9ccf-3a7b21f353e1
ms.author: windowsdriverdev
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelObject::SetContextForDataModel, SetContextForDataModel, IModelObject.SetContextForDataModel, IModelObject::SetContextForDataModel, IModelObject.SetContextForDataModel
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
-	IModelObject.SetContextForDataModel
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelObject::SetContextForDataModel


## -description

The SetContextForDataModel method is used by the implementation of a data model to place implementation data on instance objects. Conceptually, each IModelObject (call this the instance for simplicity) contains a hash table of state. The hash table is indexed by another IModelObject (call this the data model for simplicity) which is in the parent model hierarchy of the instance. The value contained in this hash is a set of reference counted state information represented by an IUnknown instance. Once the data model sets this state on the instance it can store arbitrary implementation data which can be retrieved during things like property getters. 

It is often the case that extensions (or other data model components) want to represent some synthetic construct as what one might consider a type. The debugger's exposing of process objects is one such example. Frequently, an implementation will map the notion of a type definition to a data model. The data model will contain property getters for the things which are exposed on the object (e.g.: process name, process id, thread count, threads, etc...). When it is time to create an instance of this data model, a blank synthetic object is created and the data model (or what we might consider the type definition) is attached as a parent model. In some cases, enough information to uniquely identify the object and implement all of the data model's' property getters might be able to be directly placed on the instance object. In our process example, the process id might be stored as a key named Id on the instance. When a getter on the data model is called, say for the process name, for example, the implementation can simply call the GetKeyValue method to fetch the process Id. The implementation necessary to return the name can then do so from the PID. In other cases, the state required to implement the type is more complex, contains other native constructs, or for other reasons cannot be set as an instance key. In such cases, the data model will construct an IUnknown derived class, place the implementation data within this class, and call the SetContextForDataModel method on the instance in order to associate its implementation data with the instance object. When the instance destructs, the reference count on the state class will be released and it will be freed as required


## -parameters

### -param dataModelObject
The IModelObject representing the data model for which state is being stored on an instance object. This is, in effect, a hash key to the associated state object.

### -param context
The state being associated with the instance. The exact meaning of this (and any other interfaces, etc... it supports) is up to the data model making the call to set this state. The only requirement is that such state is COM reference counted.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject;          /* get an object */
ComPtr<IModelObject> spDataModelObject; /* get an attached data model (from earlier
                                           AddParentModel or from GetParentModel) anywhere in 
                                           the ancestor tree */

// Context data must be IUnknown derived.  Otherwise, implementation is opaque to the data model.
class MyContextData :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<Microsoft::WRL::RuntimeClassType::ClassicCom>,
        IUnknown
        >
{
    /* put whatever you want here */
};

ComPtr<MyContextData> spContextData = Microsoft::WRL::Make<MyContextData>();
if (SUCCEEDED(spObject->SetContextForDataModel(spDataModelObject.Get(), spContextData.Get())))
{
    // There is now context data associated with spObject (an instance) for 
    // spDataModelObject (a parent model).  This can be fetched via
    // GetContextForDataModel.  Note that spObject and spDataModelObject only need t
    // to be related.  The model does not need to be an immediate parent.
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
