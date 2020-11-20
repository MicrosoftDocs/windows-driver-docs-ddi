---
UID: NC:wdm.PALLOCATE_COMMON_BUFFER_WITH_BOUNDS
title: PALLOCATE_COMMON_BUFFER_WITH_BOUNDS (wdm.h)
description:
tech.root: kernel
ms.assetid: c376a156-c7e2-4feb-aa21-4fbce4fe72ed
ms.date: 10/19/2018
keywords: ["PALLOCATE_COMMON_BUFFER_WITH_BOUNDS callback function"]
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - PALLOCATE_COMMON_BUFFER_WITH_BOUNDS
 - wdm/PALLOCATE_COMMON_BUFFER_WITH_BOUNDS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PALLOCATE_COMMON_BUFFER_WITH_BOUNDS
 - AllocateCommonBufferWithBounds
---

# PALLOCATE_COMMON_BUFFER_WITH_BOUNDS callback function


## -description

This callback function allocates the memory for a common buffer and maps it so that it can be accessed by a master device and the CPU. The common buffer can be bound by an optional minimum and maximum logical address.


## -parameters

### -param DmaAdapter

[in] A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.

### -param MinimumAddress

[in, optional] A pointer to a variable that contains the minimum logical address for the common buffer. This parameter indicates that the buffer should be allocated from memory at and above this address. This parameter is optional and can be specified as NULL to indicate that there is no minimum address.

### -param MaximumAddress

[in, optional] A pointer to a variable that contains the maximum logical address for the common buffer. This parameter indicates that the buffer should be allocated from memory below this address. This parameter is optional and can be specified as NULL to indicate that there is no maximum address.

### -param Length

[in] The size, in bytes, of the common buffer that is to be allocated for the DMA operation.

### -param Flags

[in] The size, in bytes, of the common buffer that is to be allocated for the DMA operation.

|Flag|Meaning|
|--- |--- |
|**DOMAIN_COMMON_BUFFER_LARGE_PAGE**|The common buffer will be allocated using a larger page granularity of PAGE_SIZE * 512. Note that this can increase the chance of the allocation being unsuccessful.|

### -param CacheType

[in, optional] A pointer to a [**MEMORY_CACHING_TYPE**](ne-wdm-_memory_caching_type.md) enumeration indicating whether the routine must enable or disable cached memory in the common buffer that is to be allocated. Only values of **MmNonCached** and **MmCached** are supported. The parameter is optional and can be specified as NULL to specify the caching will be dependent upon the hardware platform default.

### -param PreferredNode

[in] The preferred NUMA node from which the memory is to be allocated. If N is the number of NUMA nodes in a multiprocessor system, *PreferredNode* is a number in the range 0 to N–1. For a one-processor system or a non-NUMA multiprocessor system, set *PreferredNode* to zero.

### -param LogicalAddress

[out] A pointer to a variable into which this routine writes the logical address that the device can use to access the common buffer. The DMA device should use this logical address instead of the physical address that is returned by a routine such as [**MmGetPhysicalAddress**](../ntddk/nf-ntddk-mmgetphysicaladdress.md).

## -returns

Returns PVOID that is the virtual address of the memory allocated for the common buffer. If the buffer cannot be allocated, then returns NULL.

## -prototype

```cpp
//Declaration

PALLOCATE_COMMON_BUFFER_WITH_BOUNDS PallocateCommonBufferWithBounds; 

// Definition

PVOID PallocateCommonBufferWithBounds 
(
	PDMA_ADAPTER DmaAdapter
	PPHYSICAL_ADDRESS MinimumAddress
	PPHYSICAL_ADDRESS MaximumAddress
	ULONG Length
	ULONG Flags
	MEMORY_CACHING_TYPE *CacheType
	NODE_REQUIREMENT PreferredNode
	PPHYSICAL_ADDRESS LogicalAddress
)
{...}

```

## -remarks

This callback function is an extended version of the [*PALLOCATE_COMMON_BUFFER_EX*](nc-wdm-pallocate_common_buffer_ex.md) routine. The following list summarizes the features that are available only in the extended version:

- The caller can specify a minimum logical address for the common buffer that is to be allocated.
- The caller can provide a caching type override that will be followed regardless of the hardware platform.
- The caller can specify the use of a larger granularity for their common buffer allocation.

## -see-also

[_DMA_OPERATIONS](ns-wdm-_dma_operations.md)

[*PALLOCATE_COMMON_BUFFER_EX*](nc-wdm-pallocate_common_buffer_ex.md)

