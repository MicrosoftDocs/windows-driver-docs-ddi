---
UID: NC:ks.PFNKSITEMFREECALLBACK
title: PFNKSITEMFREECALLBACK (ks.h)
description: A streaming minidriver's KStrItemFreeCallback routine is called to free a previously allocated create item. KStrItemFreeCallback allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary.
old-location: stream\kstritemfreecallback.htm
tech.root: stream
ms.assetid: c97bb216-a53b-47c7-9be2-2364604b4cf8
ms.date: 04/23/2018
keywords: ["PFNKSITEMFREECALLBACK callback function"]
ms.keywords: KStrItemFreeCallback, KStrItemFreeCallback routine [Streaming Media Devices], PFNKSITEMFREECALLBACK, ks/KStrItemFreeCallback, ksfunc_3d98c1cb-4984-4d82-8e58-181445f1feca.xml, stream.kstritemfreecallback
f1_keywords:
 - "ks/KStrItemFreeCallback"
 - "KStrItemFreeCallback"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
- UserDefined
api_location:
- ks.h
api_name:
- KStrItemFreeCallback
targetos: Windows
req.typenames: 
---

# PFNKSITEMFREECALLBACK callback function

## -description

A streaming minidriver's *KStrItemFreeCallback* routine is called to free a previously allocated create item. *KStrItemFreeCallback* allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary.

## -parameters

### -param CreateItem 
[in]
Specifies a create item that was previously allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectcreateitem">KsAllocateObjectCreateItem</a>.

## -remarks

The *Context* parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a> structure must contain sufficient information to perform cleanup for the create item.

The *Flags* member of the KSOBJECT_CREATE_ITEM structure indicates if it is necessary to flush security descriptor changes.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectcreateitem">KsAllocateObjectCreateItem</a>
