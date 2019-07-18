---
UID: NF:dbgmodel.IDynamicKeyProviderConcept.GetKey
title: IDynamicKeyProviderConcept::GetKey (dbgmodel.h)
description: The GetKey method on a dynamic key provider is largely an override of the GetKey method on IModelObject. 
ms.assetid: f4aaf952-3d3d-4d42-b6e9-bc716c93fdfb
ms.date: 09/19/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDynamicKeyProviderConcept.GetKey"
ms.keywords: IDynamicKeyProviderConcept::GetKey, GetKey, IDynamicKeyProviderConcept.GetKey, IDynamicKeyProviderConcept::GetKey, IDynamicKeyProviderConcept.GetKey
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
- IDynamicKeyProviderConcept.GetKey
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDynamicKeyProviderConcept::GetKey


## -description

The GetKey method on a dynamic key provider is largely an override of the GetKey method on [IModelObject](nn-dbgmodel-imodelobject.md). The dynamic key provider is expected to return the value of the key and any metadata associated with that key. In the event that the key is not present (but no other error occurs), the provider must return false in the hasKey parameter and succeed with S_OK. Failing this call is considered a failure to fetch a key and will explicitly halt the search for the key through the parent model chain. Returning false in hasKey and success will continue the search for the key. 

Note that it is perfectly legal for GetKey to return a boxed property accessor as the key. This would be semantically identical to the GetKey method on [IModelObject](nn-dbgmodel-imodelobject.md) returning a property accessor. 


## -parameters

### -param contextObject
The instance object (this pointer) for which to get a key.

### -param key
The name of the key being retrieved.

### -param keyValue
The value of the key as determined by the dynamic provider is returned here. If an error occurs in the fetch and an invalid HRESULT is returned, this may return extended error information. It is legal for the implementation of the GetKey method to return a property accessor ([IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md)).

### -param metadata
Any metadata which is associated with the key can optionally be returned here.

### -param hasKey
An indication of whether the dynamic provider has the key or not. If the provider does not have the key, it must return false here and succeed.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDynamicKeyProviderConcept interface](nn-dbgmodel-idynamickeyproviderconcept.md)
