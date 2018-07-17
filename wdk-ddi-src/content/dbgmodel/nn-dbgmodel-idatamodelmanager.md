---
UID: NN:dbgmodel.IDataModelManager
title: IDataModelManager
author: windows-driver-content
description: TBD
ms.assetid: e40a78ba-6352-4c50-bfdf-e52686ac507b
ms.author: windowsdriverdev
ms.date: 07/13/2018
ms.topic: interface
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelManager
product: Windows
targetos: Windows
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
		<td>QueryInterface</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>AddRef</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>Release</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>Close</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateNoValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateErrorObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedObjectReference</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateSyntheticObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateDataModelObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateIntrinsicObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedIntrinsicObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetModelForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetModelForType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterModelForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterModelForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterExtensionForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterExtensionForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateMetadataStore</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetRootNamespace</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterNamedModel</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterNamedModel</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>AcquireNamedModel</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

**Object Creation / Boxing Methods**

The following set of methods is used to create new objects or to box values into an IModelObject -- the core interface of the data model. 

```
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

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
