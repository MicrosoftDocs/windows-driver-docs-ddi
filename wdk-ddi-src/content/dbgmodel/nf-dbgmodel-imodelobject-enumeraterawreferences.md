---
UID: NF:dbgmodel.IModelObject.EnumerateRawReferences
title: IModelObject::EnumerateRawReferences
author: windows-driver-content
description: The EnumerateRawReferences method enumerates references to all native children (fields, base classes, etc...) of the given object.
ms.assetid: fe0e5bc3-e852-4755-81b5-e169365b3064
ms.author: windowsdriverdev
ms.date: 08/08/2018
ms.topic: method
ms.keywords: IModelObject::EnumerateRawReferences, EnumerateRawReferences, IModelObject.EnumerateRawReferences, IModelObject::EnumerateRawReferences, IModelObject.EnumerateRawReferences
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
-	IModelObject.EnumerateRawReferences
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelObject::EnumerateRawReferences


## -description

The EnumerateRawReferences method enumerates references to all native children (e.g.: fields, base classes, etc...) of the given object. 

## -parameters

### -param kind
Indicates the kind of native symbol to fetch (e.g.: a base class or a data member).

### -param searchFlags
An optional set of flags specifying the behavior of the search for the native construct.

### -param enumerator
An enumerator which will enumerate a reference (an object that is a ObjectTargetObjectReference style object) to every native child of the kind specified by the kind argument as an IRawEnumerator interface. 


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks



## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
