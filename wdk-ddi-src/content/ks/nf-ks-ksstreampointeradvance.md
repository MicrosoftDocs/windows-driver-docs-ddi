---
UID: NF:ks.KsStreamPointerAdvance
title: KsStreamPointerAdvance function (ks.h)
description: The KsStreamPointerAdvance function advances a stream pointer to the next data frame.
old-location: stream\ksstreampointeradvance.htm
tech.root: stream
ms.assetid: 98d0b8ce-5485-4584-b164-a1bc698b08ba
ms.date: 04/23/2018
keywords: ["KsStreamPointerAdvance function"]
ms.keywords: KsStreamPointerAdvance, KsStreamPointerAdvance function [Streaming Media Devices], avfunc_1c66466d-2144-4d67-ac1f-31156bc3b07d.xml, ks/KsStreamPointerAdvance, stream.ksstreampointeradvance
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
 - KsStreamPointerAdvance
 - ks/KsStreamPointerAdvance
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsStreamPointerAdvance
---

# KsStreamPointerAdvance function


## -description

The<b> KsStreamPointerAdvance </b>function advances a stream pointer to the next data frame.

## -parameters

### -param StreamPointer 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer to advance to reference the next available data frame.

## -returns

<b>KsStreamPointerAdvance </b>returns STATUS_SUCCESS to indicate a successful advancement. It returns an error code otherwise. STATUS_DEVICE_NOT_READY is the most often returned error code and often indicates that locking the stream pointer after advancement failed. In other words, <i>StreamPointer</i> references the last frame in the queue.

## -remarks

If <i>StreamPointer</i> is locked at call-time, AVStream unlocks it before advancing it. Once advanced, the stream pointer is placed back into its original state (locked or unlocked) on the new frame.

An attempt to advance a stream pointer that is unlocked always succeeds and returns STATUS_SUCCESS. Since the stream pointer is not locked, there is no way to determine if the stream pointer references actual data. The minidriver must attempt a lock to determine if the newly advanced stream pointer references a data frame or not.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvanceoffsets">KsStreamPointerAdvanceOffsets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvanceoffsetsandunlock">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerlock">KsStreamPointerLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerunlock">KsStreamPointerUnlock</a>

