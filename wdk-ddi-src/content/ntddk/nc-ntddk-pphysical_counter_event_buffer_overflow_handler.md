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

The PPHYSICAL_COUNTER_OVERFLOW_HANDLER is implemented by the client driver to handle event bufer overflows from the counters resources acquired through the <a href="..\ntddk\nf-ntddk-halallocatehardwarecounters.md">HalAllocateHardwareCounters</a> routine.

## -prototype

```
//Declaration

PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER PphysicalCounterEventBufferOverflowHandler;

// Definition

VOID PphysicalCounterEventBufferOverflowHandler
(
	PVOID EventBuffer
	SIZE_T EntrySize
	SIZE_T NumberOfEntries
	HANDLE OwningHandle
)
{...}

```

## -parameters

### -param EventBuffer

Provides a pointer to the event buffer containing the event entires.

### -param EntrySize

Provides the size of an individual event entry.

### -param NumberOfEntries

Provides the number of entries available

### -param OwningHandle

Provides the <b>HANDLE</b> corresponding to the resource set the event buffer belongs to.

## -returns

None.

## -remarks

Register your implementation of this callback function by adding a <a href="https://msdn.microsoft.com/library/windows/hardware/ff558796">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a> with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff558797">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</a> of ResourceTypeEventBuffer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff558798">PHYSICAL_COUNTER_RESOURCE_LIST</a> and then calling <a href="..\ntddk\nf-ntddk-halallocatehardwarecounters.md">HalAllocateHardwareCounters</a>.

This callback is called at IRQL = PROFILE_LEVEL. This means it must always be memory-resident. The callback should return as quickly as possible and should not attempt to do any of the following.

* Acquire or release spin locks.

* Access paged pool that is not locked in memory

* Call a pageable routine.

The callback does not need to handle clearing any overflow registers as it will be handled by the HAL.


## -see-also