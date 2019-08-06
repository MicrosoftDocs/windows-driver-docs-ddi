---
UID: NF:ks.KsStreamPointerCancelTimeout
title: KsStreamPointerCancelTimeout function (ks.h)
description: The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer.
old-location: stream\ksstreampointercanceltimeout.htm
tech.root: stream
ms.assetid: 9e1dd010-0074-45fb-b3cb-f8ea7ad15e02
ms.date: 04/23/2018
ms.keywords: KsStreamPointerCancelTimeout, KsStreamPointerCancelTimeout function [Streaming Media Devices], avfunc_9496b7be-f178-418a-87ac-d09dec988672.xml, ks/KsStreamPointerCancelTimeout, stream.ksstreampointercanceltimeout
ms.topic: function
f1_keywords:
 - "ks/KsStreamPointerCancelTimeout"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsStreamPointerCancelTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerCancelTimeout function


## -description


The<b> KsStreamPointerCancelTimeout </b>function cancels a previously scheduled time-out callback on the specified stream pointer.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer for which to cancel a registered time-out callback.


## -returns



None




## -remarks



Minidrivers should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksstreampointerscheduletimeout">KsStreamPointerScheduleTimeout</a> to schedule a time-out callback on a specified stream pointer.

The <b>KsStreamPointerCancelTimeout</b> function does not affect stream pointers that have no currently scheduled time-out callback.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksstreampointerscheduletimeout">KsStreamPointerScheduleTimeout</a>
 

 

