---
UID: NF:dbgmodel.IDataModelManager.CreateTypedObjectReference
title: IDataModelManager::CreateTypedObjectReference
description: The CreateTypedObjectReference method is semantically similar to the CreateTypedObject method excepting that it creates a reference to the underlying native/language construct.
ms.assetid: a71dc31c-72e9-4633-a38b-6951336d759a
ms.date: 07/17/2018
ms.topic: method
ms.keywords: IDataModelManager::CreateTypedObjectReference, CreateTypedObjectReference, IDataModelManager.CreateTypedObjectReference, IDataModelManager::CreateTypedObjectReference, IDataModelManager.CreateTypedObjectReference
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
-	IDataModelManager.CreateTypedObjectReference
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::CreateTypedObjectReference


## -description

The CreateTypedObjectReference method is semantically similar to the CreateTypedObject method excepting that it creates a reference to the underlying native/language construct. The created reference is an object which has a kind of ObjectTargetObjectReference. It is not a native reference as the underlying language might support (e.g.: a C++ & or &&). It is entirely possible to have a ObjectTargetObjectReference to a C++ reference. 

An object of kind ObjectTargetObjectReference can be converted to the underlying value through use of the Dereference method on IModelObject. The reference can also be passed to the underlying host's expression evaluator in order to assign back to the value in a language appropriate way. 


## -parameters

### -param context
The debug host context in which this object is located. If no explicit context is given, the context of the newly created object will inherit from the context of the objectType argument. A caller can pass the special marker value USE_CURRENT_HOST_CONTEXT to indicate that the object should receive the context which is current in the debugger's user interface.

### -param objectLocation
The location of the object in the address space of the debug target. If the location is a virtual address, the location can be constructed by the client using a 64-bit offset into the address space; otherwise - the location must be retrieved from another debug host interface.

### -param objectType
The type of the object being constructed. The context of the type will propagate to the newly created object if no explicit context is passed in the context argument.

### -param object
The newly created object reference will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IDebugHostType> spType;       /* get a type (see CreateTypedObject) */
Location creationLocation;           /* get a location (see CreateTypedObject) */

ComPtr<IModelObject> spObjectRef;
if (SUCCEEDED(spManager->CreateTypedObjectReference(nullptr, 
                                                    creationLocation, 
                                                    spType.Get(), 
                                                    &spObjectRef)))
{
    // spObjectRef now contains a reference to the underlying object.  
    // This can be dereferenced to get the value or passed to the 
    // EE to do an assignment.
    ComPtr<IModelObject> spObject;
    if (SUCCEEDED(spObjectRef->Dereference(&spObject)))
    {
        // spObject now contains the object itself.
    }
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
