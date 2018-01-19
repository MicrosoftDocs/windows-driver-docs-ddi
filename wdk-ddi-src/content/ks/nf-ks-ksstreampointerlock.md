---
UID: NF:ks.KsStreamPointerLock
title: KsStreamPointerLock function
author: windows-driver-content
description: The KsStreamPointerLock function attempts to lock the specified stream pointer.
old-location: stream\ksstreampointerlock.htm
old-project: stream
ms.assetid: eb960301-2afa-42f7-a2ea-129d85c49db9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsStreamPointerLock
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
req.alt-api: KsStreamPointerLock
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

# KsStreamPointerLock function



## -description
The<b> KsStreamPointerLock </b>function attempts to lock the specified stream pointer.



## -syntax

````
NTSTATUS KsStreamPointerLock(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters

### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer to attempt to lock.


## -returns
<b>KsStreamPointerLock </b>returns either STATUS_SUCCESS, indicating that the stream pointer has been locked, or an appropriate error code. STATUS_DEVICE_NOT_READY is the usual error code indicating that the frame could not be locked. This error code frequently means that the frame to which <i>StreamPointer</i> was pointing was canceled.


## -remarks
A locked stream pointer guarantees that there is a data frame associated with the stream pointer and that this frame is not canceled as long as the lock is maintained. The minidriver should lock a stream pointer before attempting to access the data to which the stream pointer points.

If the pin that the stream pointer references specifies that DMA scatter/gather mappings should be generated using KSPIN_FLAG_GENERATE_MAPPINGS, AVStream generates the mappings when the stream pointer is locked.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>. 


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksstreampointerunlock.md">KsStreamPointerUnlock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerLock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

