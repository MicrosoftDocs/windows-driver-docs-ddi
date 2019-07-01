---
UID: NN:dbgmodel.IDataModelManager
title: IDataModelManager (dbgmodel.h)
description: The core interface for the data model manager.  This is the interface by which new objects are created, intrinsic values are boxed and unboxed, and models are registered for types.
ms.assetid: e40a78ba-6352-4c50-bfdf-e52686ac507b
ms.date: 07/20/2018
ms.topic: interface
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
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
- IDataModelManager
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager interface

## -description

The core interface for the data model manager.  This is the interface by which new objects are created, intrinsic values are boxed and unboxed, and models are registered for types.

This interface is never directly implemented by a client. 

## -inheritance
IDataModelManager interits from IUnknown. 
## -members

<p>IDataModelManager has these methods.</p>
<table>
	<tr>
		<td>Method</td>
		<td>Description</td>
	</tr>
    <tr>
        <td><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgmodel/nf-dbgmodel-idatamodelmanager-queryinterface">QueryInterface</a></td>
        <td> Standard COM method.Retrieves pointers to the supported interfaces on an object.</td>
    </tr>
    <tr>
        <td><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgmodel/nf-dbgmodel-idatamodelmanager-addref">AddRef</a></td>
        <td> Standard COM method. </td>
    </tr>
    <tr>
        <td><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgmodel/nf-dbgmodel-idatamodelmanager-acquirenamedmodel">AcquireNamedModel</a></td>
        <td> This looks up a well known model name and returns the data model registered by that name. Note that if there is no model registered by the supplied name, a stub will be created and returned to the caller. </td>
    </tr>
    <tr>
        <td>Release</td>
        <td> Standard COM method.</td>
    </tr>
    <tr>
        <td>Close</td>
        <td> Standard COM method.The Close method is called on the data model manager by an application (e.g.: debugger) hosting the data model in order to start the shutdown process of the data model manager. A host of the data model which does not the Close method prior to releasing its final reference on the data model manager may cause undefined behavior including, but not limited to, significant leaks of the management infrastructure for the data model.</td>
    </tr>
    <tr>
        <td>CreateNoValue</td>
        <td>The CreateNoValue method creates a "no value" object, boxes it into an IModelObject, and returns it. The returned model object has a kind of ObjectNoValue.</td>
    </tr>
    <tr>
        <td>CreateErrorObject</td>
        <td> The CreateErrorObject method creates an "error object". </td>
    </tr>
    <tr>
        <td>CreateTypedObject</td>
        <td> The CreateTypedObject method is the method which allows a client to create a representation of a native/language object in the address space of a debug target.</td>
    </tr>
    <tr>
        <td>CreateTypedObjectReference</td>
        <td> The CreateTypedObjectReference method is semantically similar to the CreateTypedObject method excepting that it creates a reference to the underlying native/language construct. The created reference is an object which has a kind of ObjectTargetObjectReference.</td>
    </tr>
    <tr>
        <td>CreateSyntheticObject</td>
        <td> The CreateSyntheticObject method creates an empty data model object -- a dictionary of key/value/metadata tuples and concepts.</td>
    </tr>
    <tr>
        <td>CreateDataModelObject</td>
        <td>The CreateDataModelObject method is a simple helper wrapper to create objects which are data models -- that is objects which are going to be attached as parent models to other objects. All such objects must support the data model concept via IDataModelConcept.</td>
    </tr>
    <tr>
        <td>CreateIntrinsicObject</td>
        <td> The CreateIntrinsicObject method is the method which boxes intrinsic values into IModelObject. The caller places the value in a COM VARIANT and calls this method. The data model manager returns an IModelObject representing the object. </td>
    </tr>
    <tr>
        <td>CreateTypedIntrinsicObject</td>
        <td>The CreateTypedintrinsicObject method is similar to the CreateIntrinsicObject method excepting that it allows a native/language type to be associated with the data and carried along with the boxed value. This allows the data model to represent constructs such as native enumeration types (which are simply VT_UI* or VT_I* values). Pointer types are also created with this method. A native pointer in the data model is a zero extended 64-bit quantity representing an offset into the virtual address space of the debug target. It is boxed inside a VT_UI8 and is created with this method and a type which indicates a native/language pointer.</td>
    </tr>
    <tr>
        <td>GetModelForTypeSignature</td>
        <td> The GetModelForTypeSignature method returns the data model that was registered against a particular type signature via a prior call to the RegisterModelForTypeSignature method. </td>
    </tr>
    <tr>
        <td>GetModelForType</td>
        <td> The GetModelForType method returns the data model which is the canonical visualizer for a given type instance. </td>
    </tr>
    <tr>
        <td>RegisterModelForTypeSignature</td>
        <td> The RegisterModelForTypeSignature method is the primary method that a caller utilizes to register a canonical visualizer for a given type (or set of types).</td>
    </tr>
    <tr>
        <td>UnregisterModelForTypeSignature</td>
        <td> The UnregisterModelForTypeSignature method undoes a prior call to the RegisterModelForTypeSignature method.</td>
    </tr>
    <tr>
        <td>RegisterExtensionForTypeSignature</td>
        <td> The RegisterExtensionForTypeSignature method is similar to the RegisterModelForTypeSignature method with one key difference. The data model which is passed to this method is not the canonical visualizer for any type and it will not take over the display of the native/language view of that type. The data model which is passed to this method will automatically be added as a parent to any concrete type which matches the supplied type signature.</td>
    </tr>
    <tr>
        <td>UnregisterExtensionForTypeSignature</td>
        <td> The UnregisterModelForTypeSignature method undoes a prior call to the RegisterModelForTypeSignature method. </td>
    </tr>
    <tr>
        <td>CreateMetadataStore</td>
        <td>The CreateMetadataStore method creates a key store -- a simplified container of key/value/metadata tuples -- which is used to hold metadata that can be associated with properties and a variety of other values. </td>
    </tr>
    <tr>
        <td>GetRootNamespace</td>
        <td> The GetRootNamespace method returns the data model's root namespace. This is an object which the data model manages and into which the debug host places certain objects. </td>
    </tr>
    <tr>
        <td>RegisterNamedModel</td>
        <td> The RegisterNamedModel method registers a given data model under a well known name so that it can be found by clients wishing to extend it.</td>
    </tr>
    <tr>
        <td>UnregisterNamedModel</td>
        <td> The UnregisterNamedModel method undoes a prior call to RegisterNamedModel. It removes the association between a data model and a name under which it can be looked up.</td>
    </tr>
</table>

## -remarks

**Object Creation / Boxing Methods**

The following set of methods is used to create new objects or to box values into an [IModelObject](nn-dbgmodel-imodelobject.md) -- the core interface of the data model. 

```cpp
STDMETHOD(CreateNoValue)(_Out_ IModelObject** object) PURE;

STDMETHOD(CreateErrorObject)(_In_ HRESULT hrError, 
                             _In_opt_ PCWSTR pwszMessage, 
                             _COM_Outptr_ IModelObject** object) PURE;

STDMETHOD(CreateTypedObject)(_In_opt_ IDebugHostContext* context, 
                             _In_ Location objectLocation, 
                             _In_ IDebugHostType* objectType, 
                             _COM_Errorptr_ IModelObject** object) PURE;

STDMETHOD(CreateTypedObjectReference)(_In_opt_ IDebugHostContext* context, 
                                      _In_ Location objectLocation, 
                                      _In_ IDebugHostType* objectType, 
                                      _COM_Errorptr_ IModelObject** object) PURE;

STDMETHOD(CreateSyntheticObject)(_In_opt_ IDebugHostContext* context, 
                                 _COM_Outptr_ IModelObject** object) PURE;

STDMETHOD(CreateDataModelObject)(_In_ IDataModelConcept* dataModel, 
                                 _COM_Outptr_ IModelObject** object) PURE;

STDMETHOD(CreateIntrinsicObject)(_In_ ModelObjectKind objectKind, 
                                 _In_ VARIANT* intrinsicData, 
                                 _COM_Outptr_ IModelObject** object) PURE;

STDMETHOD(CreateTypedIntrinsicObject)(_In_ VARIANT* intrinsicData, 
                                      _In_ IDebugHostType* type, 
                                      _COM_Outptr_ IModelObject** object) PURE;

STDMETHOD(CreateMetadataStore)(_In_opt_ IKeyStore* parentStore, 
                               _COM_Outptr_ IKeyStore** metadataStore) PURE;

STDMETHOD(CreateTypedIntrinsicObjectEx)(_In_opt_ IDebugHostContext* context, 
                                        _In_ VARIANT* intrinsicData, 
                                        _In_ IDebugHostType* type, 
                                        _COM_Outptr_ IModelObject** object) PURE;
```

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
