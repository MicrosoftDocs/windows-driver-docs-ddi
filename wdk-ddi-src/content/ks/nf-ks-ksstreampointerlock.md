---
UID: NF:ks.KsStreamPointerLock
title: KsStreamPointerLock function (ks.h)
description: The KsStreamPointerLock function attempts to lock the specified stream pointer.
old-location: stream\ksstreampointerlock.htm
tech.root: stream
ms.assetid: eb960301-2afa-42f7-a2ea-129d85c49db9
ms.date: 04/23/2018
ms.keywords: KsStreamPointerLock, KsStreamPointerLock function [Streaming Media Devices], avfunc_c7a4d7fb-9708-480d-a452-f398637bc82a.xml, ks/KsStreamPointerLock, stream.ksstreampointerlock
ms.topic: function
f1_keywords:
 - "ks/KsStreamPointerLock"
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
- KsStreamPointerLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerLock function


## -description


The<b> KsStreamPointerLock </b>function attempts to lock the specified stream pointer.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer to attempt to lock.


## -returns



<b>KsStreamPointerLock </b>returns either STATUS_SUCCESS, indicating that the stream pointer has been locked, or an appropriate error code. STATUS_DEVICE_NOT_READY is the usual error code indicating that the frame could not be locked. This error code frequently means that the frame to which <i>StreamPointer</i> was pointing was canceled.




## -remarks



A locked stream pointer guarantees that there is a data frame associated with the stream pointer and that this frame is not canceled as long as the lock is maintained. The minidriver should lock a stream pointer before attempting to access the data to which the stream pointer points.

If the pin that the stream pointer references specifies that DMA scatter/gather mappings should be generated using KSPIN_FLAG_GENERATE_MAPPINGS, AVStream generates the mappings when the stream pointer is locked.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerunlock">KsStreamPointerUnlock</a>
 

 

