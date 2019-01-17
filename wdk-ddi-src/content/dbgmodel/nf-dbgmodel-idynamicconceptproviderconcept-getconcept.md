---
UID: NF:dbgmodel.IDynamicConceptProviderConcept.GetConcept
title: IDynamicConceptProviderConcept::GetConcept
description: The GetConcept method on a dynamic concept provider is effectively an override of the GetConcept method on IModelObject.
ms.assetid: 40a661df-b934-4e3e-a4e0-6a2fbaceecbe
ms.date: 09/19/2018
ms.topic: method
ms.keywords: IDynamicConceptProviderConcept::GetConcept, GetConcept, IDynamicConceptProviderConcept.GetConcept, IDynamicConceptProviderConcept::GetConcept, IDynamicConceptProviderConcept.GetConcept
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
-	IDynamicConceptProviderConcept.GetConcept
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDynamicConceptProviderConcept::GetConcept


## -description

The GetConcept method on a dynamic concept provider is effectively an override of the GetConcept method on IModelObject. The dynamic concept provider must return an interface for the queried concept if it exists as well as any metadata associated with that concept. If the concept does not exist on the provider, that must be indicated via a false value being returned in the hasConcept argument and a successful return. Failure of this method is a failure to fetch the concept and will explicitly halt the search for the concept. Returning false for hasConcept and a successful code will continue the search for the concept through the parent model tree. 

## -parameters

### -param contextObject
The instance object (this pointer) for which to get a concept.

### -param conceptId
The GUID which identifies the concept being acquired. This GUID uniquely identifies both the concept and the core interface of the concept. It is the interface id (IID) of the primary interface for a defined concept.

### -param conceptInterface
The core interface to the concept as defined by the conceptId argument is returned here.

### -param conceptMetadata
Any metadata which is associated with the concept can optionally be returned here.

### -param hasConcept
An indication of whether the dynamic provider has the concept is returned here. If the provider does not have the concept, the value false should be returned here and the method should succeed.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also


[IDynamicConceptProviderConcept interface](nn-dbgmodel-idynamicconceptproviderconcept.md)
