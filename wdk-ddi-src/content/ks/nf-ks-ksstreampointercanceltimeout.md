---
UID: NF:ks.KsStreamPointerCancelTimeout
title: KsStreamPointerCancelTimeout function (ks.h)
description: The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer.
old-location: stream\ksstreampointercanceltimeout.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsStreamPointerCancelTimeout function"]
ms.keywords: KsStreamPointerCancelTimeout, KsStreamPointerCancelTimeout function [Streaming Media Devices], avfunc_9496b7be-f178-418a-87ac-d09dec988672.xml, ks/KsStreamPointerCancelTimeout, stream.ksstreampointercanceltimeout
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsStreamPointerCancelTimeout
 - ks/KsStreamPointerCancelTimeout
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
---

# KsStreamPointerCancelTimeout function


## -description

The<b> KsStreamPointerCancelTimeout </b>function cancels a previously scheduled time-out callback on the specified stream pointer.

## -parameters

### -param StreamPointer 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer for which to cancel a registered time-out callback.

## -remarks

Minidrivers should use <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerscheduletimeout">KsStreamPointerScheduleTimeout</a> to schedule a time-out callback on a specified stream pointer.

The <b>KsStreamPointerCancelTimeout</b> function does not affect stream pointers that have no currently scheduled time-out callback.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerscheduletimeout">KsStreamPointerScheduleTimeout</a>
