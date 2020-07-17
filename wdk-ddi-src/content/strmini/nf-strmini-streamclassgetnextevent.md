---
UID: NF:strmini.StreamClassGetNextEvent
title: StreamClassGetNextEvent function (strmini.h)
description: Minidrivers can use the StreamClassGetNextEvent routine to search the event queue of a device or of a particular stream.
old-location: stream\streamclassgetnextevent.htm
tech.root: stream
ms.assetid: a2f83163-4529-4627-8959-2b4cd6b88828
ms.date: 04/23/2018
keywords: ["StreamClassGetNextEvent function"]
ms.keywords: StreamClassGetNextEvent, StreamClassGetNextEvent routine [Streaming Media Devices], strclass-routines_5a606366-379b-400b-b039-8722f084e3c6.xml, stream.streamclassgetnextevent, strmini/StreamClassGetNextEvent
f1_keywords:
 - "strmini/StreamClassGetNextEvent"
 - "StreamClassGetNextEvent"
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
- StreamClassGetNextEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassGetNextEvent function


## -description


Minidrivers can use the <b>StreamClassGetNextEvent</b> routine to search the event queue of a device or of a particular stream.


## -parameters




### -param HwInstanceExtension_OR_HwDeviceExtension




### -param HwStreamObject [in, optional]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>. Set to <b>NULL</b> to search the event queue of the device itself. To search the event queue of a particular stream, set to the stream's stream object.


### -param EventGuid [in, optional]

Specifies the event set to match when walking the queue, or <b>NULL</b> to match any event set.


### -param EventItem [in]

Specifies the event ID to match when walking the queue, or -1 to match any event.


### -param CurrentEvent [in, optional]

Pointer to an event in the event queue, or <b>NULL</b>.


#### - HwDeviceExtension [in, optional]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


## -returns



If <i>CurrentEvent</i> is not <b>NULL</b>, <b>StreamClassGetNextEvent</b> returns the next matching event after <i>CurrentEvent</i> in the queue (or <b>NULL</b> if there is no such next event). If <i>CurrentEvent</i> is <b>NULL</b>, <b>StreamClassGetNextEvent</b> returns the first matching event in the queue.




## -remarks



The minidriver can call <b>StreamClassGetNextEvent</b> successively to loop through the event queue, examining one event at a time.

The caller may specify additional search criteria to match events on the event queue.



