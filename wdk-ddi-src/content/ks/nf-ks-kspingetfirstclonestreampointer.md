---
UID: NF:ks.KsPinGetFirstCloneStreamPointer
title: KsPinGetFirstCloneStreamPointer function (ks.h)
description: The KsPinGetFirstCloneStreamPointer function returns the first cloned stream pointer on Pin.
old-location: stream\kspingetfirstclonestreampointer.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsPinGetFirstCloneStreamPointer function"]
ms.keywords: KsPinGetFirstCloneStreamPointer, KsPinGetFirstCloneStreamPointer function [Streaming Media Devices], avfunc_2a3d17ef-c1b8-4b22-af1e-7f9bb01c1183.xml, ks/KsPinGetFirstCloneStreamPointer, stream.kspingetfirstclonestreampointer
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
 - KsPinGetFirstCloneStreamPointer
 - ks/KsPinGetFirstCloneStreamPointer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinGetFirstCloneStreamPointer
---

# KsPinGetFirstCloneStreamPointer function


## -description

The<b> KsPinGetFirstCloneStreamPointer</b> function returns the first cloned stream pointer on <i>Pin</i>.

## -parameters

### -param Pin 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure on which to return the first clone stream pointer.

## -returns

<b>KsPinGetFirstCloneStreamPointer</b> returns a pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure. This pointer points to the first cloned stream pointer on <i>Pin</i>. If no clone stream pointers exist for <i>Pin</i>, <b>KsPinGetFirstCloneStreamPointer</b> returns <b>NULL</b>.

## -remarks

<b>KsPinGetFirstCloneStreamPointer</b>, along with <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointergetnextclone">KsStreamPointerGetNextClone</a> can be used to enumerate all clone stream pointers on a given pin in the order in which they were cloned. Also see <a href="/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>



<a href="/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointergetnextclone">KsStreamPointerGetNextClone</a>
