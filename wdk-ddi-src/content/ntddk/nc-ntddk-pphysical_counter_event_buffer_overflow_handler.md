---
UID: NC:ntddk.PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER
title: PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER
author: windows-driver-content
description:
tech.root:
ms.assetid: 0166926b-64aa-48a1-a8a5-c52a4f63c1e4
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PROFILE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER
product: Windows
targetos: Windows
---

# PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER callback function

## -description

The PPHYSICAL_COUNTER_OVERFLOW_HANDLER is implemented by the client driver to handle event buffer overflows from the counters resources acquired through the [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) routine.

## -parameters

### -param EventBuffer

Provides a pointer to the event buffer containing the event entries.

### -param EntrySize

Provides the size of an individual event entry.

### -param NumberOfEntries

Provides the number of entries available.

### -param OwningHandle

Provides the <b>HANDLE</b> corresponding to the resource set the event buffer belongs to.

## -returns

None.

## -remarks

Register your implementation of this callback function by providing a [PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR](ns-ntddk-_physical_counter_resource_descriptor.md) with a [**PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE**](ne-ntddk-_physical_counter_resource_descriptor_type.md) of ResourceTypeEventBuffer to a [**PHYSICAL_COUNTER_RESOURCE_LIST**](ns-ntddk-_physical_counter_resource_list.md) and then calling [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md).

This callback is called at IRQL = PROFILE_LEVEL. This means it must always be memory-resident. The callback should return as quickly as possible and should not attempt to do any of the following.

* Acquire or release spin locks.

* Access paged pool that is not locked in memory

* Call a pageable routine.

The callback does not need to handle clearing any overflow registers as it will be handled by the HAL.


## -see-also