---
UID: NF:strmini.StreamClassCompleteRequestAndMarkQueueReady
title: StreamClassCompleteRequestAndMarkQueueReady function
author: windows-driver-content
description: The StreamClassCompleteRequestAndMarkQueueReady routine completes a request, and signals the class driver that the minidriver is ready to receive a new request of the same type.
old-location: stream\streamclasscompleterequestandmarkqueueready.htm
old-project: stream
ms.assetid: 10d08fe7-13ab-4bdb-ab91-bac3822de8ee
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: StreamClassCompleteRequestAndMarkQueueReady routine [Streaming Media Devices], strclass-routines_c94691a3-a806-4b2a-a566-7a4a9d209a6c.xml, stream.streamclasscompleterequestandmarkqueueready, StreamClassCompleteRequestAndMarkQueueReady, strmini/StreamClassCompleteRequestAndMarkQueueReady
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Stream.lib
-	Stream.dll
apiname:
-	StreamClassCompleteRequestAndMarkQueueReady
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassCompleteRequestAndMarkQueueReady function


## -description


The <b>StreamClassCompleteRequestAndMarkQueueReady</b> routine completes a request, and signals the class driver that the minidriver is ready to receive a new request of the same type.


## -syntax


````
VOID StreamClassCompleteRequestAndMarkQueueReady(
  _In_ PHW_STREAM_REQUEST_BLOCK Srb
);
````


## -parameters




### -param Srb [in]

Pointer to the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a> that the minidriver has completed processing.


## -returns



None




## -remarks



This call is equivalent to calling <b>StreamClass</b><i>Xxx</i><b>Notification</b> twice, once to signal that the request is completed, and once to signal that the minidriver is ready for the next request of that type.




## -see-also

<a href="..\strmini\nf-strmini-streamclassdevicenotification.md">StreamClassDeviceNotification</a>



<a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a>



<a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassCompleteRequestAndMarkQueueReady routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

