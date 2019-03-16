---
UID: NF:dbgmodel.IDynamicConceptProviderConcept.NotifyParentChange
title: IDynamicConceptProviderConcept::NotifyParentChange (dbgmodel.h)
description: The NotifyParent method on a dynamic concept provider is a callback made by the core data model when a static manipulation of the object's single parent model is made.
ms.assetid: 1259f0bc-bd52-41ab-91f7-852c269b223a
ms.date: 09/19/2018
ms.topic: method
ms.keywords: IDynamicConceptProviderConcept::NotifyParentChange, NotifyParentChange, IDynamicConceptProviderConcept.NotifyParentChange, IDynamicConceptProviderConcept::NotifyParentChange, IDynamicConceptProviderConcept.NotifyParentChange
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
- IDynamicConceptProviderConcept.NotifyParentChange
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDynamicConceptProviderConcept::NotifyParentChange


## -description

The NotifyParent method on a dynamic concept provider is a callback made by the core data model when a static manipulation of the object's single parent model is made. For any given parent model added, this method will be called a first time when said parent model is added and a second time if/when said parent model is removed. 

## -parameters

### -param parentModel
The parent model being added or removed from the single parent model of the dynamic concept provider object. 

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDynamicConceptProviderConcept interface](nn-dbgmodel-idynamicconceptproviderconcept.md)
