---
UID: NF:ks.KsStreamPointerScheduleTimeout
title: KsStreamPointerScheduleTimeout function
author: windows-driver-content
description: The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer.
old-location: stream\ksstreampointerscheduletimeout.htm
old-project: stream
ms.assetid: 143c4ca2-91ae-49c3-80e0-e7959e4bd297
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerScheduleTimeout, KsStreamPointerScheduleTimeout function [Streaming Media Devices], avfunc_bde904b2-cfb8-45d1-80a1-ef1046d60276.xml, ks/KsStreamPointerScheduleTimeout, stream.ksstreampointerscheduletimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsStreamPointerScheduleTimeout
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerScheduleTimeout function


## -description


The<b> KsStreamPointerScheduleTimeout </b>function registers a timeout callback with AVStream for the given stream pointer.


## -syntax


````
void KsStreamPointerScheduleTimeout(
  _In_ PKSSTREAM_POINTER  StreamPointer,
  _In_ PFNKSSTREAMPOINTER Callback,
  _In_ ULONGLONG          Interval
);
````


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer for which to register a timeout.


### -param Callback [in]

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksstreampointer.md">AVStrMiniTimeoutCallback</a> routine. If the stream pointer has not been deleted or the timeout canceled before the interval expires, AVStream calls this routine immediately following expiration of the interval.


### -param Interval [in]

Specifies the interval in 100-nanosecond units from the current time to the time that the timeout occurs.


## -returns



None




## -remarks



It is safe to call <b>KsStreamPointerScheduleTimeout</b> on a stream pointer that already has a timeout scheduled. In this case, AVStream cancels the previous timeout and replaces it with the new timeout.

<div class="alert"><b>Note</b>  If you call <b>KsStreamPointerScheduleTimeout</b> while the pin associated with the <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> is still in the pause state, the scheduled timeout may not fire unless another timeout is scheduled later in the run state. At that point, it is possible for all the timeouts that were scheduled during pause to become active and fire immediately in a chain.<p class="note">Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.

</div>
<div> </div>



## -see-also

<a href="..\ks\nf-ks-ksstreampointerdelete.md">KsStreamPointerDelete</a>



<a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a>



<a href="..\ks\nf-ks-ksstreampointercanceltimeout.md">KsStreamPointerCancelTimeout</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerScheduleTimeout function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

