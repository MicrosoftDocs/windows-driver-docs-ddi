---
UID: NF:dbgmodel.IDynamicKeyProviderConcept.EnumerateKeys
title: IDynamicKeyProviderConcept::EnumerateKeys (dbgmodel.h)
description: The EnumerateKeys method on a dynamic key provider is effectively an override of the EnumerateKeys method on IModelObject. 
ms.assetid: 26bf79c1-1069-4d9a-820a-ce00ec729e3d
ms.date: 09/19/2018
keywords: ["IDynamicKeyProviderConcept::EnumerateKeys"]
f1_keywords:
 - "dbgmodel/IDynamicKeyProviderConcept.EnumerateKeys"
 - "IDynamicKeyProviderConcept.EnumerateKeys"
ms.keywords: IDynamicKeyProviderConcept::EnumerateKeys, EnumerateKeys, IDynamicKeyProviderConcept.EnumerateKeys, IDynamicKeyProviderConcept::EnumerateKeys, IDynamicKeyProviderConcept.EnumerateKeys
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
- IDynamicKeyProviderConcept.EnumerateKeys
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDynamicKeyProviderConcept::EnumerateKeys


## -description

The EnumerateKeys method on a dynamic key provider is effectively an override of the EnumerateKeys method on [IModelObject](nn-dbgmodel-imodelobject.md). This enumerates all the keys in the dynamic provider. The returned enumerator has several restrictions that must be honored by the implementation: 

- It must behave as a call to EnumerateKeys and not EnumerateKeyValues or EnumerateKeyReferences. It must return the key values not resolving any underlying property accessors (if such concept exists in the provider).
- From the perspective of a single dynamic key provider, it is illegal to enumerate multiple keys of the same name that are physically distinct keys. This can happen on different providers that are attached through the parent model chain, but it cannot happen from the perspective of a single provider.


## -parameters

### -param contextObject
The instance object (this pointer) for which to enumerate keys.

### -param ppEnumerator
An enumerator for all keys on the dynamic provider must be returned here.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDynamicKeyProviderConcept interface](nn-dbgmodel-idynamickeyproviderconcept.md)
