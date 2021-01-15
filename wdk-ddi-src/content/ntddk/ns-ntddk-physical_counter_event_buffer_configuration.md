---
UID: NS:ntddk._PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
title: PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
description: The PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION structure describes the configuration for event buffers on the platform.
tech.root: kernel
ms.date: 01/23/2019
keywords: ["PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION structure"]
ms.keywords: PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION, PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION, *PPHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION,
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION, *PPHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - ntddk/_PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - PPHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - ntddk/PPHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - ntddk/PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - PPHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
 - PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
---

# PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION structure


## -description

The <b>PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION</b> structure describes the configuration for event buffers on the platform.

## -struct-fields

### -field OverflowHandler

A pointer to the driver-supplied [*PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER](nc-ntddk-pphysical_counter_event_buffer_overflow_handler.md) routine that will be called when the event buffer entries reach a threshold in the event buffer.

### -field CustomEventBufferEntrySize

The size of the event buffer entries, for custom event buffer sizes. Set to zero.

### -field EventThreshold

The number of events to be recorded before the OverflowHandler callback routine is invoked. This value is used as a maximum threshold. The actual number of events will depend on the number of actors using event buffer profiling.

## -remarks

Most processors have performance monitor units that contain a number of hardware counters for measuring various aspects of system performance. The <b>PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION</b> structure is used within the [**PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR**](ns-ntddk-_physical_counter_resource_descriptor.md) structure to describe the configuration for event buffer resources.

## -see-also

[**PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE**](ne-ntddk-_physical_counter_resource_descriptor_type.md)

[PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR](ns-ntddk-_physical_counter_resource_descriptor.md)

