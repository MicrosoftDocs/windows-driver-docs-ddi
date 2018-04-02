---
UID: NF:strmini.StreamClassCompleteRequestAndMarkQueueReady
title: StreamClassCompleteRequestAndMarkQueueReady function
author: windows-driver-content
description: The StreamClassCompleteRequestAndMarkQueueReady routine completes a request, and signals the class driver that the minidriver is ready to receive a new request of the same type.
old-location: stream\streamclasscompleterequestandmarkqueueready.htm
old-project: stream
ms.assetid: 10d08fe7-13ab-4bdb-ab91-bac3822de8ee
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: StreamClassCompleteRequestAndMarkQueueReady, StreamClassCompleteRequestAndMarkQueueReady routine [Streaming Media Devices], strclass-routines_c94691a3-a806-4b2a-a566-7a4a9d209a6c.xml, stream.streamclasscompleterequestandmarkqueueready, strmini/StreamClassCompleteRequestAndMarkQueueReady
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Stream.lib
-	Stream.dll
api_name:
-	StreamClassCompleteRequestAndMarkQueueReady
product:
- Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassCompleteRequestAndMarkQueueReady function


## -description


The <b>StreamClassCompleteRequestAndMarkQueueReady</b> routine completes a request, and signals the class driver that the minidriver is ready to receive a new request of the same type.


## -parameters




### -param Srb [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a> that the minidriver has completed processing.


## -returns



None




## -remarks



This call is equivalent to calling <b>StreamClass</b><i>Xxx</i><b>Notification</b> twice, once to signal that the request is completed, and once to signal that the minidriver is ready for the next request of that type.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568239">StreamClassDeviceNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568266">StreamClassStreamNotification</a>
 

 

