---
UID: NF:strmini.StreamClassStreamNotification
title: StreamClassStreamNotification function (strmini.h)
description: Streams use the StreamClassStreamNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred.
tech.root: stream
ms.date: 04/22/2022
keywords: ["StreamClassStreamNotification function"]
ms.keywords: StreamClassStreamNotification, StreamClassStreamNotification routine [Streaming Media Devices], strclass-routines_22bc1b48-b75e-4dce-9aae-16e16b1ca1f9.xml, stream.streamclassstreamnotification, strmini/StreamClassStreamNotification
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StreamClassStreamNotification
 - strmini/StreamClassStreamNotification
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
---

## -description

Streams use the **StreamClassStreamNotification** routine to notify the class driver that it has completed a stream request, or that an event has occurred.

## -parameters

### -param NotificationType [in]

This is an enumeration value that contains the type of notification that the minidriver is sending.

#### StreamRequestComplete

Indicates that the minidriver has completed its handling of the stream-oriented stream request block that is pointed to by an optional argument of this routine.

#### ReadyForNextStreamDataRequest

Indicates that this stream is ready to receive another data request.

#### ReadyForNextStreamControlRequest

Indicates that this stream is ready to receive another control request.

#### SignalStreamEvent

Signals that the event specified by an optional argument has occurred.

#### SignalMultipleStreamEvents

Signals that all events that match the criteria specified in optional arguments have occurred.

#### DeleteStreamEvent

Deletes the event specified by an optional parameter.

### -param StreamObject [in]

Points to the stream object of the stream that the class driver is being notified about.

### -param ...

## -remarks

The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use [StreamClassDeviceNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification).

## -see-also

[StreamClassDeviceNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdevicenotification)
