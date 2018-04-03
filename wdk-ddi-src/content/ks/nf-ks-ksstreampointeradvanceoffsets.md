---
UID: NF:ks.KsStreamPointerAdvanceOffsets
title: KsStreamPointerAdvanceOffsets function
author: windows-driver-content
description: The KsStreamPointerAdvanceOffsets function advances the offsets of StreamPointer.
old-location: stream\ksstreampointeradvanceoffsets.htm
old-project: stream
ms.assetid: 0377371b-b755-4473-a449-9a85e1ca456c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerAdvanceOffsets, KsStreamPointerAdvanceOffsets function [Streaming Media Devices], avfunc_31a73e93-c2b5-4867-9bb1-40090d0ea07e.xml, ks/KsStreamPointerAdvanceOffsets, stream.ksstreampointeradvanceoffsets
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsStreamPointerAdvanceOffsets
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerAdvanceOffsets function


## -description


The<b> KsStreamPointerAdvanceOffsets</b> function advances the offsets of <i>StreamPointer</i>.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure representing the stream pointer for which to advance the offsets. <i>StreamPointer</i> should be in the locked state when this function is called.


### -param InUsed [in]

The number of bytes to advance the input pointer of this stream pointer. 

(StreamPointer -&gt; OffsetIn)


### -param OutUsed [in]

The number of bytes to advance the output pointer of this stream pointer 

(StreamPointer -&gt; OffsetOut)


### -param Eject [in]

This parameter indicates whether the stream pointer should be advanced to the next data frame If this parameter is set to <b>TRUE</b>, AVStream advances the stream pointer regardless of whether advancing the offsets causes the stream pointer to point to the end of a frame.


## -returns



<b>KsStreamPointerAdvanceOffsets</b> returns STATUS_SUCCESS on success. Returns STATUS_DEVICE_NOT_READY if either <i>StreamPointer</i> was not locked at call-time or that the stream pointer could not be locked after advancement.




## -remarks



AVStream updates the in and out data pointers and other related fields by the requested values. If advancing the offsets results in zero bytes remaining in the current frame, AVStream advances the stream pointer to the next data frame and relocks it.

It is the responsibility of the minidriver to verify that <i>StreamPointer</i> is locked before calling <b>KsStreamPointerAdvanceOffsets</b>. Also, a single advancement cannot advance a stream pointer further than the beginning of the next frame in the queue. Thus, minidrivers should not attempt to advance offsets by a value greater than <i>StreamPointer -&gt; Offset*.Remaining</i>. 

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567125">KsStreamPointerAdvance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567127">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567137">KsStreamPointerUnlock</a>
 

 

