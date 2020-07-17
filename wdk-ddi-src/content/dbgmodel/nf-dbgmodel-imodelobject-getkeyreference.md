---
UID: NF:dbgmodel.IModelObject.GetKeyReference
title: IModelObject::GetKeyReference (dbgmodel.h)
description: If the object or one of its parent models has a key named according to the argument 'key', this will return a reference to that key.
ms.assetid: 6f620eb7-6074-449b-8258-273f68a735c8
ms.date: 10/03/2018
keywords: ["IModelObject::GetKeyReference"]
f1_keywords:
 - "dbgmodel/IModelObject.GetKeyReference"
 - "IModelObject.GetKeyReference"
ms.keywords: IModelObject::GetKeyReference, GetKeyReference, IModelObject.GetKeyReference, IModelObject::GetKeyReference, IModelObject.GetKeyReference
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
- IModelObject.GetKeyReference
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetKeyReference


## -description

If the object or one of its parent models has a key named according to the argument 'key', this will return a reference to that key (and optionally the *present* metadata associated with that key).

## -parameters

### -param key
The name of the key to get a value for.

### -param objectReference
The object reference.

### -param metadata
The metadata store associated with this key will be optionally returned in this argument.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
