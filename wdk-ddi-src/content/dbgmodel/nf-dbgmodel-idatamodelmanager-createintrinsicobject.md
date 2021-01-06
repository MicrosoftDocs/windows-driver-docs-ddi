---
UID: NF:dbgmodel.IDataModelManager.CreateIntrinsicObject
title: IDataModelManager::CreateIntrinsicObject (dbgmodel.h)
description: The CreateIntrinsicObject method is the method which boxes intrinsic values into IModelObject. The caller places the value in a COM VARIANT and calls this method.
ms.date: 07/17/2018
keywords: ["IDataModelManager::CreateIntrinsicObject"]
ms.keywords: IDataModelManager::CreateIntrinsicObject, CreateIntrinsicObject, IDataModelManager.CreateIntrinsicObject, IDataModelManager::CreateIntrinsicObject, IDataModelManager.CreateIntrinsicObject
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
 - IDataModelManager::CreateIntrinsicObject
 - dbgmodel/IDataModelManager::CreateIntrinsicObject
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager.CreateIntrinsicObject
---

# IDataModelManager::CreateIntrinsicObject


## -description

The CreateIntrinsicObject method is the method which boxes intrinsic values into [IModelObject](nn-dbgmodel-imodelobject.md). The caller places the value in a COM VARIANT and calls this method. The data model manager returns an [IModelObject](nn-dbgmodel-imodelobject.md) representing the object. Note that this method is also used to box fundamental IUnknown based types: property accessors, methods, contexts, etc... In such cases, the objectKind method indicates what kind of IUnknown based construct the object represents and the punkVal field of the passed variant is the IUnknown derived type. The type must be statically castable to the appropriate model interface (e.g.: [IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md), [IModelMethod](nn-dbgmodel-imodelmethod.md), [IDebugHostContext](nn-dbgmodel-idebughostcontext.md), etc...) in process. 

The VARIANT types that are supported by this method are VT_UI1, VT_I1, VT_UI2, VT_I2, VT_UI4, VT_I4, VT_UI8, VT_I8, VT_R4, VT_R8, VT_BOOL, VT_BSTR, and VT_UNKNOWN (for a specialized set of IUnknown derived types as indicated by the enumeration ModelObjectKind.

## -parameters

### -param objectKind

Indicates the kind of object which is being boxed. For normal intrinsics which differ by the variant type, ObjectIntrinsic is passed here. For others which are effectively IUnknown derived interfaces, the object type is one of the values in the ModelObjectKind enumeration and the interface in the VARIANT must match.

### -param intrinsicData

A VARIANT containing the value which is going to be boxed inside an [IModelObject](nn-dbgmodel-imodelobject.md) container.

### -param object

The newly boxed value (as an [IModelObject](nn-dbgmodel-imodelobject.md)) will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

VARIANT vtValue;
vtValue.vt = VT_I4;
vtValue.lVal = 42;

// If the object is an VT_UNKNOWN, the first argument to CreateIntrinsicObject
// indicates what KIND of IUnknown.  For example, ObjectPropertyAccessor would 
// indicate IModelPropertyAccessor.  ObjectMethod would indicate IModelMethod, etc...
ComPtr<IModelObject> spValue;
if (SUCCEEDED(spManager->CreateIntrinsicObject(ObjectIntrinsic, &vtValue, &spValue)))
{
    // spValue now contains the object (boxed) representation of the int value 42.
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)

