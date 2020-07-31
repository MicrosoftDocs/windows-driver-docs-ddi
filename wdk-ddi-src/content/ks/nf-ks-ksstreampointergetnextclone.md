---
UID: NF:ks.KsStreamPointerGetNextClone
title: KsStreamPointerGetNextClone function (ks.h)
description: The KsStreamPointerGetNextClone function returns the clone stream pointer that was cloned immediately after the specified clone.
old-location: stream\ksstreampointergetnextclone.htm
tech.root: stream
ms.assetid: b7f34d42-6044-43c6-85c8-ca3a6177c057
ms.date: 04/23/2018
keywords: ["KsStreamPointerGetNextClone function"]
ms.keywords: KsStreamPointerGetNextClone, KsStreamPointerGetNextClone function [Streaming Media Devices], avfunc_946c362b-9246-4d06-afce-e4597a16a91b.xml, ks/KsStreamPointerGetNextClone, stream.ksstreampointergetnextclone
f1_keywords:
 - "ks/KsStreamPointerGetNextClone"
 - "KsStreamPointerGetNextClone"
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
- KsStreamPointerGetNextClone
targetos: Windows
req.typenames: 
---

# KsStreamPointerGetNextClone function


## -description


The<b> KsStreamPointerGetNextClone </b>function returns the clone stream pointer that was cloned immediately after the specified clone.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the clone stream pointer for which the clone stream pointer cloned immediately after it on the same pin is returned.


## -returns



<b>KsStreamPointerGetNextClone </b>returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the clone stream pointer that was cloned immediately after <i>StreamPointer</i> on the same pin. Alternatively, it returns <b>NULL</b> indicating that either <i>StreamPointer</i> is the last clone on the pin or that <i>StreamPointer</i> is not a clone. If not a clone, <i>StreamPointer</i> is either the leading or trailing edge stream pointer.




## -remarks



The returned pointer always refers to the same pin as <i>StreamPointer</i>. <b>KsStreamPointerGetNextClone</b>, in conjunction with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>,<b></b>can be used to enumerate all clone stream pointers on a given pin in the order in which they were cloned.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerdelete">KsStreamPointerDelete</a>
 

 

