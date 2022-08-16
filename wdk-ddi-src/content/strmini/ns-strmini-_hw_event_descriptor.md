---
UID: NS:strmini._HW_EVENT_DESCRIPTOR
title: _HW_EVENT_DESCRIPTOR (strmini.h)
description: When the class driver calls one of the minidriver's StrMiniEvent routines, it passes a pointer to an HW_EVENT_DESCRIPTOR structure to describe the event as enabled or disabled.
tech.root: stream
ms.date: 08/16/2022
keywords: ["HW_EVENT_DESCRIPTOR structure"]
ms.keywords: "*PHW_EVENT_DESCRIPTOR, HW_EVENT_DESCRIPTOR, HW_EVENT_DESCRIPTOR structure [Streaming Media Devices], PHW_EVENT_DESCRIPTOR, PHW_EVENT_DESCRIPTOR structure pointer [Streaming Media Devices], _HW_EVENT_DESCRIPTOR, strclass-struct_ca0c15b2-17d1-4114-9765-5638dd81ca24.xml, stream.hw_event_descriptor, strmini/HW_EVENT_DESCRIPTOR, strmini/PHW_EVENT_DESCRIPTOR"
req.header: strmini.h
req.include-header: Strmini.h
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
targetos: Windows
req.typenames: HW_EVENT_DESCRIPTOR, *PHW_EVENT_DESCRIPTOR
f1_keywords:
 - _HW_EVENT_DESCRIPTOR
 - strmini/_HW_EVENT_DESCRIPTOR
 - PHW_EVENT_DESCRIPTOR
 - strmini/PHW_EVENT_DESCRIPTOR
 - HW_EVENT_DESCRIPTOR
 - strmini/HW_EVENT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - strmini.h
api_name:
 - _HW_EVENT_DESCRIPTOR
 - PHW_EVENT_DESCRIPTOR
 - HW_EVENT_DESCRIPTOR
---

## -description

When the class driver calls one of the minidriver's [StrMiniEvent](./nc-strmini-phw_event_routine.md) routines, it passes a pointer to an HW_EVENT_DESCRIPTOR structure to describe the event as enabled or disabled.

## -struct-fields

### -field Enable

This is set to **TRUE** for an enabled event, and **FALSE** for a disabled event.

### -field EventEntry

Points to the [KSEVENT_ENTRY](../ks/ns-ks-_ksevent_entry.md) structure that describes this event.

### -field EventData

Points to the [KSEVENTDATA](../ks/ns-ks-kseventdata.md) structure that describes this instance of the event.

### -field StreamObject

Points to the [HW_STREAM_OBJECT](./ns-strmini-_hw_stream_object.md) for the stream that owns the event that the class driver is enabling/disabling, or **NULL** if the event belongs to the driver as a whole.

### -field DeviceExtension

Points to the minidriver's device extension.

### -field EnableEventSetIndex

For stream events, this specifies the index of the event set within the **StreamEventsArray** member of the stream's [HW_STREAM_INFORMATION](./ns-strmini-_hw_stream_information.md) structure.

For device events, this specifies the index of the event set within the **DeviceEventsArray** member of the minidriver's [HW_STREAM_HEADER](./ns-strmini-_hw_stream_header.md) structure.

### -field HwInstanceExtension

Pointer to the minidriver's instance extension. The minidriver may use this buffer to record private information global to this instance of the minidriver. The minidriver sets the size of this buffer in the [HW_INITIALIZATION_DATA](./ns-strmini-_hw_initialization_data.md) structure it passes when it registers itself via [StreamClassRegisterMinidriver](./nf-strmini-streamclassregisteradapter.md).

### -field Reserved

Reserved for system use. Do not use.

### -field Reserved[2]

Reserved for system use. Do not use.
