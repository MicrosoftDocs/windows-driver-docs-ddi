---
UID: NF:dbgmodel.IDynamicConceptProviderConcept.SetConcept
title: IDynamicConceptProviderConcept::SetConcept
author: windows-driver-content
description: TBD
ms.assetid: f65dace2-4cb8-4395-a16e-6467aa9c282e
ms.author: windowsdriverdev
ms.date: 09/19/2018
ms.topic: method
ms.keywords: IDynamicConceptProviderConcept::SetConcept, SetConcept, IDynamicConceptProviderConcept.SetConcept, IDynamicConceptProviderConcept::SetConcept, IDynamicConceptProviderConcept.SetConcept
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
-	IDynamicConceptProviderConcept.SetConcept
product: Windows
targetos: Windows
tech.root: debugger
---

# IDynamicConceptProviderConcept::SetConcept


## -description

The SetConcept method on a dynamic concept provider is effectively an override of the SetConcept method on IModelObject. The dynamic provider will assign the concept. This may make the object iterable, indexable, string convertible, etc... Note that a provider which does not allow the creation of concepts on it should return E_NOPTIMPL here. 

## -parameters

### -param contextObject
The instance object (this pointer) on which a concept is being created.

### -param conceptId
The GUID which identifies the concept being assigned. This GUID uniquely identifies both the concept and the core interface of the concept. It is the interface id (IID) of the primary interface for a defined concept.

### -param conceptInterface
The core interface to the concept as defined by the conceptId argument.

### -param conceptMetadata
Optional metadata to be associated with the concept.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also


[IDynamicConceptProviderConcept interface](nn-dbgmodel-idynamicconceptproviderconcept.md)
