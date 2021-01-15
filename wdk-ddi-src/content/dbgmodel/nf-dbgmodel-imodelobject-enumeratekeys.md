---
UID: NF:dbgmodel.IModelObject.EnumerateKeys
title: IModelObject::EnumerateKeys (dbgmodel.h)
description: Enumerates the keys within the dynamic key provider.
ms.date: 07/20/2018
keywords: ["IModelObject::EnumerateKeys"]
ms.keywords: IModelObject::EnumerateKeys, EnumerateKeys, IModelObject.EnumerateKeys, IModelObject::EnumerateKeys, IModelObject.EnumerateKeys
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
 - IModelObject::EnumerateKeys
 - dbgmodel/IModelObject::EnumerateKeys
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelObject::EnumerateKeys
---

# IModelObject::EnumerateKeys


## -description

Enumerates the keys within the dynamic key provider.  The returned enumerator must behave as per an EnumerateKeys(...) call on [IModelObject](nn-dbgmodel-imodelobject.md) and not as EnumerateKeyValues or any of the other enumeration variants.

Note that from the perspective of a single dynamic key provider, it is illegal to enumerate multiple keys of the same name that are physically distinct keys.

## -parameters

### -param enumerator

An enumerator for all keys on the object (and all of its parent models) and their values and metadata is returned in this argument as an [IKeyEnumerator](nn-dbgmodel-ikeyenumerator.md).

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

The EnumerateKeys method behaves similar to the EnumerateKeyValues method excepting that it does not automatically resolve property accessors on the object. This means that if the value of a key is a property accessor, the EnumerateKeys method will return the property accessor (an IModelPropertyAccessorInterface) boxed into an [IModelObject](nn-dbgmodel-imodelobject.md) rather than automatically calling the GetValue method. This is similar to the difference between GetKey and GetKeyValue.

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)

