---
UID: NN:dbgmodel.IDataModelManager
title: IDataModelManager (dbgmodel.h)
description: The core interface for the data model manager.  This is the interface by which new objects are created, intrinsic values are boxed and unboxed, and models are registered for types.
ms.assetid: e40a78ba-6352-4c50-bfdf-e52686ac507b
ms.date: 07/20/2018
f1_keywords:
 - "dbgmodel/IDataModelManager"
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
