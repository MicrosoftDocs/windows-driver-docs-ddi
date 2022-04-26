---
UID: NF:strmini.StreamClassDeviceNotification
title: StreamClassDeviceNotification function (strmini.h)
description: Minidrivers use the StreamClassDeviceNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred.
tech.root: stream
ms.date: 04/22/2022
keywords: ["StreamClassDeviceNotification function"]
ms.keywords: StreamClassDeviceNotification, StreamClassDeviceNotification routine [Streaming Media Devices], strclass-routines_bddec484-f87c-4ebc-b8e1-ea52d265cbc4.xml, stream.streamclassdevicenotification, strmini/StreamClassDeviceNotification
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
 - StreamClassDeviceNotification
 - strmini/StreamClassDeviceNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Stream.lib
 - Stream.dll
api_name:
 - StreamClassDeviceNotification
---

## -description

Minidrivers use the **StreamClassDeviceNotification** routine to notify the class driver that it has completed a stream request, or that an event has occurred.

## -parameters

### -param NotificationType [in]

This is an enumeration value that contains the type of notification that the minidriver is sending.

#### DeviceRequestComplete

Indicates that the minidriver has completed its handling of the device stream request block. Once the minidriver calls **StreamClassDeviceNotification** with this value, the relevant SRB is owned by the class driver, which is free to deallocate it.

#### ReadyForNextDeviceRequest

Indicates that the minidriver is ready to receive another device request.

#### SignalDeviceEvent

Signals that the event specified by an optional parameter has occurred.

#### SignalMultipleDeviceEvents

Signals all events that match the criteria specified in optional parameters.

#### DeleteDeviceEvent

Deletes the event specified by an optional parameter.

### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the [HW_INITIALIZATION_DATA](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure it passes when it registers itself via [StreamClassRegisterMinidriver](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter). The class driver then passes pointers to the buffer in the **HwDeviceExtension** member of the [HW_STREAM_REQUEST_BLOCK](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block), [HW_STREAM_OBJECT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object), [HW_TIME_CONTEXT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context), and [PORT_CONFIGURATION_INFORMATION](/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information) structures it passes to the minidriver.

### -param ...

## -remarks

The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use [StreamClassStreamNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassstreamnotification).

## -see-also

[StreamClassStreamNotification](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassstreamnotification)
