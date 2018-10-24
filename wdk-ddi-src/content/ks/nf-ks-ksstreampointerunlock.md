---
UID: NF:ks.KsStreamPointerUnlock
title: KsStreamPointerUnlock function
author: windows-driver-content
description: The KsStreamPointerUnlock function unlocks a stream pointer that has previously been locked by an acquisition function (KsGetXxxEdgeStreamPointer) or by KsStreamPointerLock.
old-location: stream\ksstreampointerunlock.htm
tech.root: stream
ms.assetid: 1d03b97f-5c01-48b2-a0e4-2dc6bf732813
ms.date: 04/23/2018
ms.keywords: KsStreamPointerUnlock, KsStreamPointerUnlock function [Streaming Media Devices], avfunc_71260371-8ee2-45e1-ad72-7eba8212d081.xml, ks/KsStreamPointerUnlock, stream.ksstreampointerunlock
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
-	KsStreamPointerUnlock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerUnlock function


## -description


The<b> KsStreamPointerUnlock </b>function unlocks a stream pointer that has previously been locked by an acquisition function <b>(KsGet</b><i>Xxx</i><b>EdgeStreamPointer</b>) or by <b>KsStreamPointerLock</b>.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure representing the stream pointer to unlock.


### -param Eject [in]

This parameter specifies whether to advance <i>StreamPointer</i> to the next data frame. A value of <b>TRUE</b> advances the stream pointer.


## -returns



None




## -remarks



<b>KsStreamPointerUnlock</b> can also advance the stream pointer to the next data frame. See the description of <i>Eject</i> above.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a>



<b>KsPinGetLeadingEdgeStreamPointer</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567125">KsStreamPointerAdvance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567126">KsStreamPointerAdvanceOffsets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567127">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>
 

 

