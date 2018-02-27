---
UID: NF:ks.KsStreamPointerAdvance
title: KsStreamPointerAdvance function
author: windows-driver-content
description: The KsStreamPointerAdvance function advances a stream pointer to the next data frame.
old-location: stream\ksstreampointeradvance.htm
old-project: stream
ms.assetid: 98d0b8ce-5485-4584-b164-a1bc698b08ba
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerAdvance, KsStreamPointerAdvance function [Streaming Media Devices], avfunc_1c66466d-2144-4d67-ac1f-31156bc3b07d.xml, ks/KsStreamPointerAdvance, stream.ksstreampointeradvance
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
-	KsStreamPointerAdvance
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerAdvance function


## -description


The<b> KsStreamPointerAdvance </b>function advances a stream pointer to the next data frame.


## -syntax


````
NTSTATUS KsStreamPointerAdvance(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer to advance to reference the next available data frame.


## -returns



<b>KsStreamPointerAdvance </b>returns STATUS_SUCCESS to indicate a successful advancement. It returns an error code otherwise. STATUS_DEVICE_NOT_READY is the most often returned error code and often indicates that locking the stream pointer after advancement failed. In other words, <i>StreamPointer</i> references the last frame in the queue.




## -remarks



If <i>StreamPointer</i> is locked at call-time, AVStream unlocks it before advancing it. Once advanced, the stream pointer is placed back into its original state (locked or unlocked) on the new frame.

An attempt to advance a stream pointer that is unlocked always succeeds and returns STATUS_SUCCESS. Since the stream pointer is not locked, there is no way to determine if the stream pointer references actual data. The minidriver must attempt a lock to determine if the newly advanced stream pointer references a data frame or not.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also

<a href="..\ks\nf-ks-ksstreampointeradvanceoffsets.md">KsStreamPointerAdvanceOffsets</a>



<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>



<a href="..\ks\nf-ks-ksstreampointerunlock.md">KsStreamPointerUnlock</a>



<a href="..\ks\nf-ks-ksstreampointeradvanceoffsetsandunlock.md">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerAdvance function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

