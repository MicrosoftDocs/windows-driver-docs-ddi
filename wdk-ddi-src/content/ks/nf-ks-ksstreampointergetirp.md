---
UID: NF:ks.KsStreamPointerGetIrp
title: KsStreamPointerGetIrp function
author: windows-driver-content
description: The KsStreamPointerGetIrp function returns the IRP associated with the frame that is referenced by the given stream pointer.
old-location: stream\ksstreampointergetirp.htm
old-project: stream
ms.assetid: 3ed4ed2f-66be-4429-b2d6-2d9d3f9bcf3e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerGetIrp, KsStreamPointerGetIrp function [Streaming Media Devices], avfunc_57ecd1af-c967-473c-b475-1d91bc42f2eb.xml, ks/KsStreamPointerGetIrp, stream.ksstreampointergetirp
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
-	KsStreamPointerGetIrp
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerGetIrp function


## -description


The<b> KsStreamPointerGetIrp </b>function returns the IRP associated with the frame that is referenced by the given stream pointer.


## -parameters




### -param StreamPointer [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure that references the frame for which the associated IRP is returned.


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

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567132">KsStreamPointerGetMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerGetIrp function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

