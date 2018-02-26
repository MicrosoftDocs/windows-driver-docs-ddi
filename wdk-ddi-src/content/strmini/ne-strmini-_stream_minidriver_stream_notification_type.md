---
UID: NE:strmini._STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE
title: "_STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE"
author: windows-driver-content
description: "."
old-location: stream\stream_minidriver_stream_notification_type.htm
old-project: stream
ms.assetid: 13D8152C-FE7E-46EB-9C7F-9CA0135A4B76
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PSTREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, ,, A, C, D, DeleteStreamEvent, E, F, HardwareStarved, I, M, N, O, P, PSTREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, PSTREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE enumeration pointer [Streaming Media Devices], R, ReadyForNextStreamControlRequest, ReadyForNextStreamDataRequest, S, STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE enumeration [Streaming Media Devices], SignalMultipleStreamEvents, SignalStreamEvent, StreamNotificationMaximum, StreamRequestComplete, T, V, Y, _, _STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, stream.stream_minidriver_stream_notification_type, strmini/DeleteStreamEvent, strmini/HardwareStarved, strmini/PSTREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, strmini/ReadyForNextStreamControlRequest, strmini/ReadyForNextStreamDataRequest, strmini/STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, strmini/SignalMultipleStreamEvents, strmini/SignalStreamEvent, strmini/StreamNotificationMaximum, strmini/StreamRequestComplete"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Strmini.h
apiname:
-	STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE
product: Windows
targetos: Windows
req.typenames: STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, *PSTREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# _STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE enumeration


## -description





## -syntax


````
typedef enum _STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE { 
  ReadyForNextStreamDataRequest,
  ReadyForNextStreamControlRequest,
  HardwareStarved,
  StreamRequestComplete,
  SignalMultipleStreamEvents,
  SignalStreamEvent,
  DeleteStreamEvent,
  StreamNotificationMaximum
} STREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE, *PSTREAM_MINIDRIVER_STREAM_NOTIFICATION_TYPE;
````


## -enum-fields




### -field ReadyForNextStreamDataRequest

Indicates that the minidriver is ready for the next stream data request.


### -field ReadyForNextStreamControlRequest

Indicates that the minidriver is ready for the next stream control request.


### -field HardwareStarved

Indicates that the hardware is starved for data.


### -field StreamRequestComplete

Indicates that the specified stream SRB has completed.


### -field SignalMultipleStreamEvents


### -field SignalStreamEvent


### -field DeleteStreamEvent


### -field StreamNotificationMaximum

