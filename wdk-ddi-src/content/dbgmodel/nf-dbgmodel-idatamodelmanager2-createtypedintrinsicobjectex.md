---
UID: NF:dbgmodel.IDataModelManager2.CreateTypedIntrinsicObjectEx
title: IDataModelManager2::CreateTypedIntrinsicObjectEx (dbgmodel.h)
description: The CreateTypedIntrinsicObjectEx method is semantically similar to the CreateTypedIntrinsicObject method.
ms.date: 09/11/2018
keywords: ["IDataModelManager2::CreateTypedIntrinsicObjectEx"]
ms.keywords: IDataModelManager2::CreateTypedIntrinsicObjectEx, CreateTypedIntrinsicObjectEx, IDataModelManager2.CreateTypedIntrinsicObjectEx, IDataModelManager2::CreateTypedIntrinsicObjectEx, IDataModelManager2.CreateTypedIntrinsicObjectEx
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
 - IDataModelManager2::CreateTypedIntrinsicObjectEx
 - dbgmodel/IDataModelManager2::CreateTypedIntrinsicObjectEx
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager2::CreateTypedIntrinsicObjectEx
---

# IDataModelManager2::CreateTypedIntrinsicObjectEx


## -description

The CreateTypedIntrinsicObjectEx method is semantically similar to the CreateTypedIntrinsicObject method. The only difference between the two is that this method allows the caller to specify the context in which the intrinsic data is valid. If no context is passed, the data is considered valid in whatever context is inherited from the type argument (how CreateTypedIntrinsicObject behaves). This allows for the creation of typed pointer values in the debug target which require more specific context than can be inherited from the type.

## -parameters

### -param context

The context which should be associated with the newly created object. If this is not specified, the context of the object will inherit from the context of the type argument. The special value USE_CURRENT_HOST_CONTEXT can also be passed indicating that the context should be the current UI context of the debugger.

### -param intrinsicData

A VARIANT containing the value which is going to be boxd inside an [IModelObject](nn-dbgmodel-imodelobject.md) container. Note that this method does not support VT_UNKNOWN constructs. Anything passed to this method must be expressable as ObjectIntrinsic

### -param type

The native/language type of the value.

### -param object

The newly boxed value (as an [IModelObject](nn-dbgmodel-imodelobject.md)) will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)

