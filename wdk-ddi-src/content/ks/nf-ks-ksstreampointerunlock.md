---
UID: NF:ks.KsStreamPointerUnlock
title: KsStreamPointerUnlock function (ks.h)
description: The KsStreamPointerUnlock function unlocks a stream pointer that has previously been locked by an acquisition function (KsGetXxxEdgeStreamPointer) or by KsStreamPointerLock.
old-location: stream\ksstreampointerunlock.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsStreamPointerUnlock function"]
ms.keywords: KsStreamPointerUnlock, KsStreamPointerUnlock function [Streaming Media Devices], avfunc_71260371-8ee2-45e1-ad72-7eba8212d081.xml, ks/KsStreamPointerUnlock, stream.ksstreampointerunlock
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
 - KsStreamPointerUnlock
 - ks/KsStreamPointerUnlock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsStreamPointerUnlock
---

# KsStreamPointerUnlock function


## -description

The<b> KsStreamPointerUnlock </b>function unlocks a stream pointer that has previously been locked by an acquisition function <b>(KsGet</b><i>Xxx</i><b>EdgeStreamPointer</b>) or by <b>KsStreamPointerLock</b>.

## -parameters

### -param StreamPointer [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer to unlock.

### -param Eject [in]


This parameter specifies whether to advance <i>StreamPointer</i> to the next data frame. A value of <b>TRUE</b> advances the stream pointer.

## -remarks

<b>KsStreamPointerUnlock</b> can also advance the stream pointer to the next data frame. See the description of <i>Eject</i> above.

Also see <a href="/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>



<b>KsPinGetLeadingEdgeStreamPointer</b>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvance">KsStreamPointerAdvance</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvanceoffsets">KsStreamPointerAdvanceOffsets</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvanceoffsetsandunlock">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="/windows-hardware/drivers/devtest/ks-ksstreampointerlock">KsStreamPointerLock</a>
