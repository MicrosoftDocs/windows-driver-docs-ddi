---
UID: NF:dbgmodel.IModelObject.GetKind
title: IModelObject::GetKind (dbgmodel.h)
description: The GetKind method returns what kind of object is boxed inside the IModelObject.
ms.date: 06/10/2019
keywords: ["IModelObject::GetKind"]
ms.keywords: IModelObject::GetKind, GetKind, IModelObject.GetKind, IModelObject::GetKind, IModelObject.GetKind
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
 - IModelObject::GetKind
 - dbgmodel/IModelObject::GetKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelObject::GetKind
---

# IModelObject::GetKind


## -description

The GetKind method returns what kind of object is boxed inside the [IModelObject](nn-dbgmodel-imodelobject.md). Such kind is defined by the [ModelObjectKind enumeration](./ne-dbgmodel-modelobjectkind.md).

## -parameters

### -param kind

The kind of object as indicated above will be returned in this argument.

## -returns

This method returns HRESULT that indicates success or failure. This method should not typically fail.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* acquired from somewhere */

ModelObjectKind kind;
HRESULT hr = spObject->GetKind(&kind);

// kind indicates the kind of model object
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)

