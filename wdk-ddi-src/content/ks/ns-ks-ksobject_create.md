---
UID: NS:ks.__unnamed_struct_77
title: KSOBJECT_CREATE (ks.h)
description: The KSOBJECT_CREATE structure contains an array of create handlers for base object classes supported by this device object.
old-location: stream\ksobject_create.htm
tech.root: stream
ms.assetid: b59d76eb-77c2-4ae5-8be2-f987d7f58446
ms.date: 04/23/2018
keywords: ["KSOBJECT_CREATE structure"]
ms.keywords: "*PKSOBJECT_CREATE, KSOBJECT_CREATE, KSOBJECT_CREATE structure [Streaming Media Devices], PKSOBJECT_CREATE, PKSOBJECT_CREATE structure pointer [Streaming Media Devices], ks-struct_885122dd-299b-47d0-b161-2d3ffac610f6.xml, ks/KSOBJECT_CREATE, ks/PKSOBJECT_CREATE, stream.ksobject_create"
f1_keywords:
 - "ks/KSOBJECT_CREATE"
 - "KSOBJECT_CREATE"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSOBJECT_CREATE
targetos: Windows
req.typenames: KSOBJECT_CREATE, *PKSOBJECT_CREATE
---

# KSOBJECT_CREATE structure


## -description


The KSOBJECT_CREATE structure contains an array of create handlers for base object classes supported by this device object.


## -struct-fields




### -field CreateItemsCount

Contains the number of items in the following array.


### -field CreateItemsList

Points to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a> structures for base object classes supported by this device object.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a>
 

 

