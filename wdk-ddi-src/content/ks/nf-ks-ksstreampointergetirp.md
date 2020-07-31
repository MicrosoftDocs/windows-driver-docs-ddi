---
UID: NF:ks.KsStreamPointerGetIrp
title: KsStreamPointerGetIrp function (ks.h)
description: The KsStreamPointerGetIrp function returns the IRP associated with the frame that is referenced by the given stream pointer.
old-location: stream\ksstreampointergetirp.htm
tech.root: stream
ms.assetid: 3ed4ed2f-66be-4429-b2d6-2d9d3f9bcf3e
ms.date: 04/23/2018
keywords: ["KsStreamPointerGetIrp function"]
ms.keywords: KsStreamPointerGetIrp, KsStreamPointerGetIrp function [Streaming Media Devices], avfunc_57ecd1af-c967-473c-b475-1d91bc42f2eb.xml, ks/KsStreamPointerGetIrp, stream.ksstreampointergetirp
f1_keywords:
 - "ks/KsStreamPointerGetIrp"
 - "KsStreamPointerGetIrp"
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
- KsStreamPointerGetIrp
targetos: Windows
req.typenames: 
---

# KsStreamPointerGetIrp function


## -description


The<b> KsStreamPointerGetIrp </b>function returns the IRP associated with the frame that is referenced by the given stream pointer.


## -parameters




### -param StreamPointer [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure that references the frame for which the associated IRP is returned.


### -param FirstFrameInIrp [out, optional]

A pointer to a caller-supplied BOOLEAN value set to <b>TRUE</b> on return if the frame referenced by <i>StreamPointer</i> is the first frame in the returned IRP and <b>FALSE</b> if not. If <b>NULL</b>, AVStream does not test this condition.


### -param LastFrameInIrp [out, optional]

A pointer to a caller-supplied BOOLEAN value set to <b>TRUE</b> if the frame referenced by the stream pointer is the last frame in the returned IRP and <b>FALSE</b> if not. If <b>NULL</b>, AVStream does not test this condition.


## -returns



<b>KsStreamPointerGetIrp </b>returns either a pointer to the IRP associated with the frame that is referenced by the given stream pointer, or returns <b>NULL</b>. A return value of <b>NULL</b> indicates that the stream pointer is not locked.




## -remarks



<b>KsStreamPointerGetIrp </b>can also be used to determine if <i>StreamPointer</i> references the first and/or last frame contained in the returned IRP.

<i>StreamPointer</i> must be locked in order for <b>KsStreamPointerGetIrp </b>to execute successfully. Any attempt to call this function with an unlocked stream pointer results in a <b>NULL</b> return value.

<i>FirstFrameInIrp </i>and<i>/</i>or <i>LastFrameInIrp</i> must be non-<b>NULL</b> at call-time in order for AVStream to fill in these values.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointergetmdl">KsStreamPointerGetMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerlock">KsStreamPointerLock</a>
 

 

