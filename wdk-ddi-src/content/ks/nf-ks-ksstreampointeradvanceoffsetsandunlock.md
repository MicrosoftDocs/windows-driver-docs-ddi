---
UID: NF:ks.KsStreamPointerAdvanceOffsetsAndUnlock
title: KsStreamPointerAdvanceOffsetsAndUnlock function (ks.h)
description: The KsStreamPointerAdvanceOffsetsAndUnlock function advances StreamPointer the specified number of bytes into the stream (adjusting the OffsetIn and OffsetOut fields of StreamPointer as requested) and unlocks it.
old-location: stream\ksstreampointeradvanceoffsetsandunlock.htm
tech.root: stream
ms.assetid: bb15eb8e-b609-4110-b0de-71efb8ef1f5e
ms.date: 04/23/2018
ms.keywords: KsStreamPointerAdvanceOffsetsAndUnlock, KsStreamPointerAdvanceOffsetsAndUnlock function [Streaming Media Devices], avfunc_5f1d19bb-e367-4df3-9423-0263bda1cd54.xml, ks/KsStreamPointerAdvanceOffsetsAndUnlock, stream.ksstreampointeradvanceoffsetsandunlock
f1_keywords:
 - "ks/KsStreamPointerAdvanceOffsetsAndUnlock"
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
- KsStreamPointerAdvanceOffsetsAndUnlock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerAdvanceOffsetsAndUnlock function


## -description


The<b> KsStreamPointerAdvanceOffsetsAndUnlock</b> function advances <i>StreamPointer</i> the specified number of bytes into the stream (adjusting the <i>OffsetIn </i>and <i>OffsetOut </i>fields of <i>StreamPointer</i> as requested) and unlocks it.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer to advance and unlock.


### -param InUsed [in]

This parameter contains the number of input bytes used. AVStream advances the input offset by this number of bytes. This must be less than the total number of remaining unused bytes in the frame referenced by <i>StreamPointer</i>. If <i>InUsed</i> is equal to the remaining number of bytes in the frame referenced by <i>StreamPointer</i>, AVStream advances <i>StreamPointer </i>to the next available data frame.


### -param OutUsed [in]

This parameter contains the number of output bytes used. AVStream advances the output offset by this number of bytes. This must be less than the total number of remaining unused bytes in the frame referenced by <i>StreamPointer</i>. If <i>OutUsed</i> is equal to the remaining number of bytes in the frame referenced by <i>StreamPointer</i>, AVStream advances <i>StreamPointer </i>to the next available data frame.


### -param Eject [in]

This parameter indicates whether <i>StreamPointer</i> should be advanced. If this parameter is set to <b>TRUE</b>, AVStream advances the stream pointer to the next available data frame regardless of the values in <i>InUsed </i>and <i>OutUsed</i>.


## -remarks



If using the specified number of bytes in the stream pointer results in zero remaining bytes to process in the current frame, AVStream advances the stream pointer to the next available frame. Minidrivers can force advancement to the next frame regardless of the number of bytes used by setting <i>Eject</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvance">KsStreamPointerAdvance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerdelete">KsStreamPointerDelete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerlock">KsStreamPointerLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerunlock">KsStreamPointerUnlock</a>
 

 

