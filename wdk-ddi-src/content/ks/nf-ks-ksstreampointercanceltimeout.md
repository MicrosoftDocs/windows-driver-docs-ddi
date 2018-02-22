---
UID: NF:ks.KsStreamPointerCancelTimeout
title: KsStreamPointerCancelTimeout function
author: windows-driver-content
description: The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer.
old-location: stream\ksstreampointercanceltimeout.htm
old-project: stream
ms.assetid: 9e1dd010-0074-45fb-b3cb-f8ea7ad15e02
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsStreamPointerCancelTimeout function [Streaming Media Devices], avfunc_9496b7be-f178-418a-87ac-d09dec988672.xml, stream.ksstreampointercanceltimeout, ks/KsStreamPointerCancelTimeout, KsStreamPointerCancelTimeout
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsStreamPointerCancelTimeout
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerCancelTimeout function


## -description


The<b> KsStreamPointerCancelTimeout </b>function cancels a previously scheduled time-out callback on the specified stream pointer.


## -syntax


````
void KsStreamPointerCancelTimeout(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer for which to cancel a registered time-out callback.


## -returns



None




## -remarks



Minidrivers should use <a href="..\ks\nf-ks-ksstreampointerscheduletimeout.md">KsStreamPointerScheduleTimeout</a> to schedule a time-out callback on a specified stream pointer.

The <b>KsStreamPointerCancelTimeout</b> function does not affect stream pointers that have no currently scheduled time-out callback.




## -see-also

<a href="..\ks\nf-ks-kspingetfirstclonestreampointer.md">KsPinGetFirstCloneStreamPointer</a>



<a href="..\ks\nf-ks-ksstreampointerscheduletimeout.md">KsStreamPointerScheduleTimeout</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerCancelTimeout function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

