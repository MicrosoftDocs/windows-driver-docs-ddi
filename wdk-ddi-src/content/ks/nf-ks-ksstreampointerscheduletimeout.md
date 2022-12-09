---
UID: NF:ks.KsStreamPointerScheduleTimeout
title: KsStreamPointerScheduleTimeout function (ks.h)
description: The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer.
tech.root: stream
ms.date: 11/16/2022
keywords: ["KsStreamPointerScheduleTimeout function"]
ms.keywords: KsStreamPointerScheduleTimeout, KsStreamPointerScheduleTimeout function [Streaming Media Devices], avfunc_bde904b2-cfb8-45d1-80a1-ef1046d60276.xml, ks/KsStreamPointerScheduleTimeout, stream.ksstreampointerscheduletimeout
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
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsStreamPointerScheduleTimeout
 - ks/KsStreamPointerScheduleTimeout
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
---

## -description

The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer.

## -parameters

### -param StreamPointer [in]

A pointer to a [**KSSTREAM_POINTER**](./ns-ks-_ksstream_pointer.md) structure representing the stream pointer for which to register a timeout.

### -param Callback [in]

A pointer to a minidriver-supplied [AVStrMiniTimeoutCallback](/previous-versions/windows/hardware/drivers/ff556362(v=vs.85)) routine. If the stream pointer has not been deleted or the timeout canceled before the interval expires, AVStream calls this routine immediately following expiration of the interval.

### -param Interval [in]

Specifies the interval in 100-nanosecond units from the current time to the time that the timeout occurs.

## -remarks

It is safe to call KsStreamPointerScheduleTimeout on a stream pointer that already has a timeout scheduled. In this case, AVStream cancels the previous timeout and replaces it with the new timeout.

> [!NOTE]
> If you call KsStreamPointerScheduleTimeout while the pin associated with the [**KSSTREAM_POINTER**](./ns-ks-_ksstream_pointer.md) is still in the pause state, the scheduled timeout may not fire unless another timeout is scheduled later in the run state. At that point, it is possible for all the timeouts that were scheduled during pause to become active and fire immediately in a chain. Also see [Stream Pointers](/windows-hardware/drivers/stream/stream-pointers).

## -see-also

[**KSSTREAM_POINTER**](./ns-ks-_ksstream_pointer.md)

[KsStreamPointerCancelTimeout](./nf-ks-ksstreampointercanceltimeout.md)

[KsStreamPointerDelete](./nf-ks-ksstreampointerdelete.md)