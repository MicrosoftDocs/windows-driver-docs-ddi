---
UID: NF:strmini.StreamClassStreamNotification
title: StreamClassStreamNotification function (strmini.h)
description: Streams use the StreamClassStreamNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred.
old-location: stream\streamclassstreamnotification.htm
tech.root: stream
ms.assetid: 67dd0ea0-9c69-415a-8b37-0e8700b6fbd8
ms.date: 04/23/2018
keywords: ["StreamClassStreamNotification function"]
ms.keywords: StreamClassStreamNotification, StreamClassStreamNotification routine [Streaming Media Devices], strclass-routines_22bc1b48-b75e-4dce-9aae-16e16b1ca1f9.xml, stream.streamclassstreamnotification, strmini/StreamClassStreamNotification
f1_keywords:
 - "strmini/StreamClassStreamNotification"
 - "StreamClassStreamNotification"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassStreamNotification
targetos: Windows
req.typenames: 
---

# StreamClassStreamNotification function


## -description


Streams use the <b>StreamClassStreamNotification</b> routine to notify the class driver that it has completed a stream request, or that an event has occurred.


## -parameters




### -param NotificationType [in]

This is an enumeration value that contains the type of notification that the minidriver is sending.





#### StreamRequestComplete

Indicates that the minidriver has completed its handling of the stream-oriented stream request block that is pointed to by the optional third argument of this routine, <i>pSrb</i>.



#### ReadyForNextStreamDataRequest

Indicates that this stream is ready to receive another data request. 



#### ReadyForNextStreamControlRequest

Indicates that this stream is ready to receive another control request. 



#### SignalStreamEvent

Signals that the event specified by the <i>EventEntry</i> parameter has occurred.



#### SignalMultipleStreamEvents

Signals that all events that match the criteria specified in the <i>EventSet</i> and <i>EventId</i> parameters have occurred.



#### DeleteStreamEvent

Deletes the event specified by the <i>EventEntry</i> parameter.


### -param StreamObject [in]

Points to the stream object of the stream that the class driver is being notified about.


### -param param






#### - EventEntry

Specify only if <i>NotificationType</i> equals either <b>SignalStreamEvent</b> or <b>DeleteStreamEvent</b>. Pointer to the event to be signaled or deleted. This parameter is optional. 


#### - EventId

Indicates the event ID against which to match in the event queue for this stream. Specify only if <i>NotificationType</i> equals <b>SignalMultipleStreamEvents</b>. This parameter is optional.


#### - EventSet

Identifies the event set against which to match in the event queue for this stream. Specify only if <i>NotificationType</i> equals <b>SignalMultipleStreamEvents</b>. This parameter is optional. 


#### - pSrb

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a> structure. Specify only if <i>NotificationType</i> equals <b>StreamRequestComplete</b>. Pointer to the stream request block that the minidriver has completed processing. Once this routine completes, this address is no longer valid. This parameter is optional.


## -remarks



The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification">StreamClassDeviceNotification</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification">StreamClassDeviceNotification</a>
 

 

