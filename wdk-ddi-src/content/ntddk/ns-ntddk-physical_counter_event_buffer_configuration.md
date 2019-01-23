---
UID: NS:ntddk._PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
title: PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
author: windows-driver-content
description:
tech.root:
ms.assetid: a593133a-8ce9-450a-8330-6b25c250be06
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
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
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION
product: Windows
targetos: Windows
---

# PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION structure

## -description

The <b>PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION</b> structure describes the configuration for event buffers on the platform.

## -struct-fields

### -field OverflowHandler

A pointer to the <a href="..\ntddk\nc-ntddk-pphysical_counter_event_buffer_overflow_handler.md">PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER</a> routine that will be called when the event buffer entries reach a threshold in the event buffer.


### -field CustomEventBufferEntrySize

The size of the event buffer entries, for custom event buffer sizes. This should be set to 0.


### -field EventThreshold

The number of events to be recorded before the EventBufferOverflowHandler is invoked. This value is used as a maximum threshold. The actual number of events will depend on the number of actors using event buffer profiling.

## -remarks

Most processors have performance monitor units that contain a number of hardware counters for measuring various aspects of system performance. The <b>PHYSICAL_COUNTER_EVENT_BUFFER_CONFIGURATION</b> structure is used within the <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure to describe the configuration for event buffer resources.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558797">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558796">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a>