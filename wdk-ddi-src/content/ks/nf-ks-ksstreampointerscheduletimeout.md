---
UID: NF:ks.KsStreamPointerScheduleTimeout
title: KsStreamPointerScheduleTimeout function (ks.h)
description: The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer.
old-location: stream\ksstreampointerscheduletimeout.htm
tech.root: stream
ms.assetid: 143c4ca2-91ae-49c3-80e0-e7959e4bd297
ms.date: 04/23/2018
ms.keywords: KsStreamPointerScheduleTimeout, KsStreamPointerScheduleTimeout function [Streaming Media Devices], avfunc_bde904b2-cfb8-45d1-80a1-ef1046d60276.xml, ks/KsStreamPointerScheduleTimeout, stream.ksstreampointerscheduletimeout
ms.topic: function
f1_keywords:
 - "ks/KsStreamPointerScheduleTimeout"
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
- KsStreamPointerScheduleTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerScheduleTimeout function


## -description


The<b> KsStreamPointerScheduleTimeout </b>function registers a timeout callback with AVStream for the given stream pointer.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer for which to register a timeout.


### -param Callback [in]

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff556362(v=vs.85)">AVStrMiniTimeoutCallback</a> routine. If the stream pointer has not been deleted or the timeout canceled before the interval expires, AVStream calls this routine immediately following expiration of the interval.


### -param Interval [in]

Specifies the interval in 100-nanosecond units from the current time to the time that the timeout occurs.


## -returns



None




## -remarks



It is safe to call <b>KsStreamPointerScheduleTimeout</b> on a stream pointer that already has a timeout scheduled. In this case, AVStream cancels the previous timeout and replaces it with the new timeout.

<div class="alert"><b>Note</b>  If you call <b>KsStreamPointerScheduleTimeout</b> while the pin associated with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> is still in the pause state, the scheduled timeout may not fire unless another timeout is scheduled later in the run state. At that point, it is possible for all the timeouts that were scheduled during pause to become active and fire immediately in a chain.<p class="note">Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.

</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksstreampointercanceltimeout">KsStreamPointerCancelTimeout</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksstreampointerdelete">KsStreamPointerDelete</a>
 

 

