---
UID: NF:strmini.StreamClassGetNextEvent
title: StreamClassGetNextEvent function (strmini.h)
description: Minidrivers can use the StreamClassGetNextEvent routine to search the event queue of a device or of a particular stream.
tech.root: stream
ms.date: 04/22/2022
keywords: ["StreamClassGetNextEvent function"]
ms.keywords: StreamClassGetNextEvent, StreamClassGetNextEvent routine [Streaming Media Devices], strclass-routines_5a606366-379b-400b-b039-8722f084e3c6.xml, stream.streamclassgetnextevent, strmini/StreamClassGetNextEvent
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
 - StreamClassGetNextEvent
 - strmini/StreamClassGetNextEvent
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
---

## -description

Minidrivers can use the **StreamClassGetNextEvent** routine to search the event queue of a device or of a particular stream.

## -parameters

### -param HwInstanceExtension_OR_HwDeviceExtension [in, optional]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the [HW_INITIALIZATION_DATA](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure it passes when it registers itself via [StreamClassRegisterMinidriver](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter). The class driver then passes pointers to the buffer in the **HwDeviceExtension** member of the [HW_STREAM_REQUEST_BLOCK](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block), [HW_STREAM_OBJECT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object), [HW_TIME_CONTEXT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context), and [PORT_CONFIGURATION_INFORMATION](/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information) structures it passes to the minidriver.

This first parameter was PVOID HwDeviceExtension. It MUST be HwInstanceExtension for multi-instance and multi-filter types (version 20) drivers. Legacy single instance drivers can continue to specify HwDeviceExtension as the first parameter. It can also specify HwInstanceExtension.

### -param HwStreamObject [in, optional]

Pointer to a [HW_STREAM_OBJECT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object). Set to **NULL** to search the event queue of the device itself. To search the event queue of a particular stream, set to the stream's stream object.

### -param EventGuid [in, optional]

Specifies the event set to match when walking the queue, or **NULL** to match any event set.

### -param EventItem [in]

Specifies the event ID to match when walking the queue, or -1 to match any event.

### -param CurrentEvent [in, optional]

Pointer to an event in the event queue, or **NULL**.

## -returns

If *CurrentEvent* is not **NULL**, **StreamClassGetNextEvent** returns the next matching event after *CurrentEvent* in the queue (or **NULL** if there is no such next event). If *CurrentEvent* is **NULL**, **StreamClassGetNextEvent** returns the first matching event in the queue.

## -remarks

The minidriver can call **StreamClassGetNextEvent** successively to loop through the event queue, examining one event at a time.

The caller may specify additional search criteria to match events on the event queue.
