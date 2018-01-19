---
UID: NF:ks.KsStreamPointerUnlock
title: KsStreamPointerUnlock function
author: windows-driver-content
description: The KsStreamPointerUnlock function unlocks a stream pointer that has previously been locked by an acquisition function (KsGetXxxEdgeStreamPointer) or by KsStreamPointerLock.
old-location: stream\ksstreampointerunlock.htm
old-project: stream
ms.assetid: 1d03b97f-5c01-48b2-a0e4-2dc6bf732813
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsStreamPointerUnlock
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
req.alt-api: KsStreamPointerUnlock
req.alt-loc: Ks.lib,Ks.dll
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
req.typenames: 
---

# KsStreamPointerUnlock function



## -description
The<b> KsStreamPointerUnlock </b>function unlocks a stream pointer that has previously been locked by an acquisition function <b>(KsGet</b><i>Xxx</i><b>EdgeStreamPointer</b>) or by <b>KsStreamPointerLock</b>.



## -syntax

````
void KsStreamPointerUnlock(
  _In_ PKSSTREAM_POINTER StreamPointer,
  _In_ BOOLEAN           Eject
);
````


## -parameters

### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer to unlock.


### -param Eject [in]

This parameter specifies whether to advance <i>StreamPointer</i> to the next data frame. A value of <b>TRUE</b> advances the stream pointer.


## -returns
None


## -remarks
<b>KsStreamPointerUnlock</b> can also advance the stream pointer to the next data frame. See the description of <i>Eject</i> above.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointeradvance.md">KsStreamPointerAdvance</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointeradvanceoffsets.md">KsStreamPointerAdvanceOffsets</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksstreampointeradvanceoffsetsandunlock.md">KsStreamPointerAdvanceOffsetsAndUnlock</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetleadingedgestreampointer.md">KsPinGetLeadingEdgeStreamPointer</a>
</dt>
<dt><b>KsPinGetLeadingEdgeStreamPointer</b></dt>
<dt>
<a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerUnlock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

