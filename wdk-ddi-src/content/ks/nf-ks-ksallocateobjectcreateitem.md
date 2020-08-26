---
UID: NF:ks.KsAllocateObjectCreateItem
title: KsAllocateObjectCreateItem function (ks.h)
description: The KsAllocateObjectCreateItem function allocates a slot for the specified create item, optionally allocating space for and copying the create item data as well.
old-location: stream\ksallocateobjectcreateitem.htm
tech.root: stream
ms.assetid: 43c3894c-5568-4cba-80ed-1d4e4388547b
ms.date: 04/23/2018
keywords: ["KsAllocateObjectCreateItem function"]
ms.keywords: KsAllocateObjectCreateItem, KsAllocateObjectCreateItem function [Streaming Media Devices], ks/KsAllocateObjectCreateItem, ksfunc_57773cdc-d649-4381-9841-deba5beddf73.xml, stream.ksallocateobjectcreateitem
f1_keywords:
 - "ks/KsAllocateObjectCreateItem"
 - "KsAllocateObjectCreateItem"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAllocateObjectCreateItem
targetos: Windows
req.typenames: 
---

# KsAllocateObjectCreateItem function


## -description


The <b>KsAllocateObjectCreateItem</b> function allocates a slot for the specified create item, optionally allocating space for and copying the create item data as well. This function assumes that the caller is serializing multiple changes to the create entry list.


## -parameters




### -param Header 
[in]
Points to the device header on which to attach the create item.


### -param CreateItem 
[in]
Contains the create item to attach.


### -param AllocateEntry 
[in]
Indicates whether the create item pointer passed should be attached directly to the header, or if a copy of it should be made instead.


### -param ItemFreeCallback 
[in, optional]
Optionally contains a pointer to a minidriver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksitemfreecallback">KStrItemFreeCallback</a> function to be called when the create entry is being destroyed upon freeing the device header. This is only valid when <i>AllocateEntry</i> is <b>TRUE</b>.


## -returns



Returns STATUS_SUCCESS if a new item was allocated and attached. Otherwise, it returns STATUS_INSUFFICIENT_RESOURCES.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksitemfreecallback">KStrItemFreeCallback</a>
 

 

