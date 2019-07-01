---
UID: NF:dbgmodel.IModelObject.GetTypeInfo
title: IModelObject::GetTypeInfo (dbgmodel.h)
description: The GetTypeInfo method will return the native type of the given object. If the object does not have native type information associated with it the call will still succeed but will return null. 
ms.assetid: 15543aee-79aa-45e7-ad7a-017eab0e7d74
ms.date: 06/10/2019
ms.topic: method
ms.keywords: IModelObject::GetTypeInfo, GetTypeInfo, IModelObject.GetTypeInfo, IModelObject::GetTypeInfo, IModelObject.GetTypeInfo
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IModelObject.GetTypeInfo
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetTypeInfo

## -description

The GetTypeInfo method will return the native type of the given object. If the object does not have native type information associated with it (e.g.: it is an intrinsic, etc...), the call will still succeed but will return null.

## -parameters

### -param type

The native type of the object represented by the this pointer will be returned here as an [IDebugHostType](nn-dbgmodel-idebughosttype.md) interface.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

In this sample the [IDebugHostType interface](nn-dbgmodel-idebughosttype.md) is used.

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ComPtr<IDebugHostType> spType;
if (SUCCEEDED(spObject->GetTypeInfo(&spType)) && spType != nullptr)
{
    // The object has a native type.  spType is such type.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
