---
UID: NF:dbgmodel.IModelObject.EnumerateKeyReferences
title: IModelObject::EnumerateKeyReferences (dbgmodel.h)
description: The EnumerateKeyReferences method behaves similar to the EnumerateKeyValues method excepting that it returns references to the keys it enumerates instead of the value of the key.
ms.assetid: 85aace53-f325-4f74-acea-9661aef591c1
ms.date: 07/20/2018
ms.topic: method
ms.keywords: IModelObject::EnumerateKeyReferences, EnumerateKeyReferences, IModelObject.EnumerateKeyReferences, IModelObject::EnumerateKeyReferences, IModelObject.EnumerateKeyReferences
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
- IModelObject.EnumerateKeyReferences
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::EnumerateKeyReferences


## -description

The EnumerateKeyReferences method behaves similar to the EnumerateKeyValues method excepting that it returns references to the keys it enumerates (given by an [IModelKeyReference](nn-dbgmodel-imodelkeyreference.md) interface boxed into an [IModelObject](nn-dbgmodel-imodelobject.md)) instead of the value of the key. Such references can be used to get or set the underlying value of the keys. 

## -parameters

### -param enumerator

An enumerator for references to all keys on the object (and all of its parent models) and metadata is returned in this argument as an [IKeyEnumerator](nn-dbgmodel-ikeyenumerator.md).


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
