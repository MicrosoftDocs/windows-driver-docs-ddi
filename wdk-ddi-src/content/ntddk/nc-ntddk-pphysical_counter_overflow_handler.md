---
UID: NC:ntddk.PPHYSICAL_COUNTER_OVERFLOW_HANDLER
title: PPHYSICAL_COUNTER_OVERFLOW_HANDLER
author: windows-driver-content
description: The PPHYSICAL_COUNTER_OVERFLOW_HANDLER is implemented by the client driver to handle overflows from the counters resources acquired through the HalAllocateHardwareCounters routine.
tech.root:
ms.assetid: 49f5213b-3b7e-4bdc-9f4d-16c06e602fba
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
req.header: ntddk.h
req.include-header:
req.target-type: Windows
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
 - PPHYSICAL_COUNTER_OVERFLOW_HANDLER
product: Windows
targetos: Windows
---

# PPHYSICAL_COUNTER_OVERFLOW_HANDLER callback function

## -description

The PPHYSICAL_COUNTER_OVERFLOW_HANDLER is implemented by the client driver to handle counter overflows from the counters resources acquired through the [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) routine.

## -parameters

### -param OverflowBits

Provides a bitmap describing which counters overflowed.

### -param OwningHandle

Provides the <b>HANDLE</b> corresponding to the resource set the overflowing counters belong to.



## -returns

None.

## -remarks

Register your implementation of this callback function by calling [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) with a structure of type [**PHYSICAL_COUNTER_RESOURCE_LIST**](ns-ntddk-_physical_counter_resource_list.md).  In the **PHYSICAL_COUNTER_RESOURCE_LIST**, provide a structure of type [PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR](ns-ntddk-_physical_counter_resource_descriptor.md) that specifies a [**PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE**](ne-ntddk-_physical_counter_resource_descriptor_type.md) of **ResourceTypeOverflow**.

This callback is called at IRQL = PROFILE_LEVEL. This means it must always be memory-resident. The callback should return as quickly as possible and should not attempt to do any of the following.

* Acquire or release spin locks.

* Access paged pool that is not locked in memory

* Call a pageable routine.

The callback does not need to handle clearing any overflow registers as it will be handled by the HAL.

## -see-also
