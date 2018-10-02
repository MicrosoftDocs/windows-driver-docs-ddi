---
UID: NF:dbgmodel.IDynamicKeyProviderConcept.SetKey
title: IDynamicKeyProviderConcept::SetKey
author: windows-driver-content
description: TBD
ms.assetid: 8ab2d7b7-8e07-45d8-9de1-e04de3c0f448
ms.author: windowsdriverdev
ms.date: 09/19/2018
ms.topic: method
ms.keywords: IDynamicKeyProviderConcept::SetKey, SetKey, IDynamicKeyProviderConcept.SetKey, IDynamicKeyProviderConcept::SetKey, IDynamicKeyProviderConcept.SetKey
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
-	IDynamicKeyProviderConcept.SetKey
product: Windows
targetos: Windows
tech.root: debugger
---

# IDynamicKeyProviderConcept::SetKey


## -description

The SetKey method on a dynamic key provider is effectively an override of the SetKey method on IModelObject. This sets a key in the dynamic provider. It is effectively the creation of a new property on the provider. Note that a provider which does not support any notion of something like the creation of expando properties should return E_NOTIMPL here. 

## -parameters

### -param contextObject
The instance object (this pointer) for which to set a key.

### -param key
The name of the key to set.

### -param keyValue
The value of the key to set.

### -param metadata
Optional metadata to be associated with the (newly created) key.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDynamicKeyProviderConcept interface](nn-dbgmodel-idynamickeyproviderconcept.md)
