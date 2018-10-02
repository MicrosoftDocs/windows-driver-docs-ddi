---
UID: NF:dbgmodel.IDynamicConceptProviderConcept.NotifyParent
title: IDynamicConceptProviderConcept::NotifyParent
author: windows-driver-content
description: TBD
ms.assetid: 200f5925-57bf-4b7d-b187-39b5daab0992
ms.author: windowsdriverdev
ms.date: 09/19/2018 
ms.topic: method
ms.keywords: IDynamicConceptProviderConcept::NotifyParent, NotifyParent, IDynamicConceptProviderConcept.NotifyParent, IDynamicConceptProviderConcept::NotifyParent, IDynamicConceptProviderConcept.NotifyParent
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
-	IDynamicConceptProviderConcept.NotifyParent
product: Windows
targetos: Windows
tech.root: debugger
---

# IDynamicConceptProviderConcept::NotifyParent


## -description

The NotifyParent call on a dynamic concept provider is used by the core data model to inform the dynamic provider of the single parent model which is created to allow for bridging the "multiple parent models" paradigm of the data model to more dynamic languages. Any manipulation of that single parent model will cause further notifications to the dynamic provider. Note that this callback is made immediately upon assignment of the dynamic concept provider concept. 

## -parameters

### -param parentModel
The single parent model created by the data model to help bridge the multiple parent paradigm of the data model to more dynamic languages. The dynamic provider should save this argument as it will only be notified of this once upon assignment of the dynamic concept provider concept.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDynamicConceptProviderConcept interface](nn-dbgmodel-idynamicconceptproviderconcept.md)
