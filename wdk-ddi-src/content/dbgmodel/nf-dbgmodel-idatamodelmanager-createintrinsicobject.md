---
UID: NF:dbgmodel.IDataModelManager.CreateIntrinsicObject
title: IDataModelManager::CreateIntrinsicObject
author: windows-driver-content
description: TBD
ms.assetid: 0fc6ec51-85d8-4df2-b26e-33b0bd5ed172
ms.author: windowsdriverdev
ms.date:  07/17/2018
ms.topic: method
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
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelManager.CreateIntrinsicObject
product: Windows
targetos: Windows


---

# IDataModelManager::CreateIntrinsicObject


## -description

The CreateIntrinsicObject method is the method which boxes intrinsic values into IModelObject. The caller places the value in a COM VARIANT and calls this method. The data model manager returns an IModelObject representing the object. Note that this method is also used to box fundamental IUnknown based types: property accessors, methods, contexts, etc... In such cases, the objectKind method indicates what kind of IUnknown based construct the object represents and the punkVal field of the passed variant is the IUnknown derived type. The type must be statically castable to the appropriate model interface (e.g.: IModelPropertyAccessor, IModelMethod, IDebugHostContext, etc...) in process. 

The VARIANT types that are supported by this method are VT_UI1, VT_I1, VT_UI2, VT_I2, VT_UI4, VT_I4, VT_UI8, VT_I8, VT_R4, VT_R8, VT_BOOL, VT_BSTR, and VT_UNKNOWN (for a specialized set of IUnknown derived types as indicated by the enumeration ModelObjectKind. 


## -parameters

### -param objectKind

Indicates the kind of object which is being boxed. For normal intrinsics which differ by the variant type, ObjectIntrinsic is passed here. For others which are effectively IUnknown derived interfaces, the object type is one of the values in the ModelObjectKind enumeration and the interface in the VARIANT must match.


### -param intrinsicData
A VARIANT containing the value which is going to be boxed inside an IModelObject container.

### -param object
The newly boxed value (as an IModelObject) will be returned here.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```

```


## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)