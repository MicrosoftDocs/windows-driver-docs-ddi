---
UID: NC:ks.PFNKSIRPLISTCALLBACK
title: PFNKSIRPLISTCALLBACK
author: windows-driver-content
description: A streaming minidriver's KStrIrpListCallback routine is called to determine whether the passed in IRP should be moved from the source list to the destination list, or if IRP enumeration should be terminated.
old-location: stream\kstrirplistcallback.htm
old-project: stream
ms.assetid: acddecb5-f3e9-413e-a68c-91d71119e0f6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrIrpListCallback, KStrIrpListCallback routine [Streaming Media Devices], PFNKSIRPLISTCALLBACK, ks/KStrIrpListCallback, ksfunc_90be2b49-883f-476a-9d01-d1e1296844ab.xml, stream.kstrirplistcallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	KStrIrpListCallback
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSIRPLISTCALLBACK callback


## -description


A streaming minidriver's <i>KStrIrpListCallback</i> routine is called to determine whether the passed in IRP should be moved from the source list to the destination list, or if IRP enumeration should be terminated.


## -parameters




### -param Irp [in]

Pointer to the IRP to possibly move to the destination list from the source list.


### -param Context [in]

Passed from <a href="https://msdn.microsoft.com/library/windows/hardware/ff563434">KsMoveIrpsOnCancelableQueue</a>.


## -returns



Returns STATUS_SUCCESS to indicate the passed in IRP should be moved from the source list to the destination list. Returns STATUS_NO_MATCH if the passed in IRP should not be moved. Returns any other value to terminate enumeration.




## -remarks



<i>KStrIrpListCallback</i> is called at DISPATCH_LEVEL.

<i>KStrIrpListCallback</i> is always called at least once at the end of list processing with a <b>NULL</b> IRP value in order to complete list processing.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563434">KsMoveIrpsOnCancelableQueue</a>
 

 

