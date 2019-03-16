---
UID: NC:ks.PFNKSITEMFREECALLBACK
title: PFNKSITEMFREECALLBACK (ks.h)
description: A streaming minidriver's KStrItemFreeCallback routine is called to free a previously allocated create item. KStrItemFreeCallback allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary.
old-location: stream\kstritemfreecallback.htm
tech.root: stream
ms.assetid: c97bb216-a53b-47c7-9be2-2364604b4cf8
ms.date: 04/23/2018
ms.keywords: KStrItemFreeCallback, KStrItemFreeCallback routine [Streaming Media Devices], PFNKSITEMFREECALLBACK, ks/KStrItemFreeCallback, ksfunc_3d98c1cb-4984-4d82-8e58-181445f1feca.xml, stream.kstritemfreecallback
ms.topic: callback
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSITEMFREECALLBACK callback function


## -description


A streaming minidriver's <i>KStrItemFreeCallback</i> routine is called to free a previously allocated create item. <i>KStrItemFreeCallback</i> allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary.


## -parameters




### -param CreateItem [in]

Specifies a create item that was previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560968">KsAllocateObjectCreateItem</a>.


## -returns



Returns STATUS_SUCCESS if the passed in create item was successfully freed, or the error code that was returned from the minidriver's attempt to free the create item in <i>KStrItemFreeCallback</i>.




## -remarks



The <i>Context</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a> structure must contain sufficient information to perform cleanup for the create item.

The <i>Flags</i> member of the KSOBJECT_CREATE_ITEM structure indicates if it is necessary to flush security descriptor changes.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560968">KsAllocateObjectCreateItem</a>
 

 

