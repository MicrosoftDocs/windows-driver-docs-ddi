---
UID: NS:wdm._IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
tech.root: kernel
title: IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
ms.date: 06/09/2021
targetos: Windows
description: The IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG structure contains information required to configure a logical allocator.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG, *PIOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - PIOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
f1_keywords:
 - _IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - wdm/_IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - PIOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - wdm/PIOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
 - wdm/IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG
dev_langs:
 - c++
---

## -description

The **IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG** structure contains information required to configure a logical allocator.

This structure is used by [*IOMMU_DOMAIN_CREATE_EX*](nc-wdm-iommu_domain_create_ex.md) to create a logical allocator attached to the created [**IOMMU_DMA_DOMAIN**].

## -struct-fields

### -field LogicalAllocatorType

An [**IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE**](ne-wdm-iommu_dma_logical_allocator_type.md) value that indicates the type of logical allocator to be created.

### -field BuddyAllocatorConfig

Provides configuration information specific to the HAL Buddy Allocator.

### -field BuddyAllocatorConfig.AddressWidth

Provides the address width for the allocator to be created. 32-bit operating systems are limited to a width of 32 bits, while 64-bit operating systems are limited to a width of 63 bits. When creating a domain, the address width should correspond to the maximum address width for the device(s) expected to be attached.

## -remarks

With [*IOMMU_DOMAIN_CREATE_EX*](nc-wdm-iommu_domain_create_ex.md), a caller may opt to attach a logical allocator to the domain being created.

When interacting with such a domain, a caller does not need to keep track of previous mappings. Instead, the logical allocator takes responsibility for determining the logical address to be used when mapping physical pages to the owning domain. The logical allocator is also responsible for maintaining state to ensure that logical address collisions do not occur.

Currently the only logical allocator type available is the Buddy Allocator. This allocator favors low logical addresses and will allocate logical addresses on power of two boundaries at or above 4KB. The allocator is also augmented with a cache of free logical address values to improve the performance of free address lookup.

The Buddy Allocator does not allow for explicit address allocation. Calling [*IOMMU_MAP_IDENTITY_RANGE_EX*](nc-wdm-iommu_map_identity_range_ex.md) or [*IOMMU_MAP_LOGICAL_RANGE_EX*](nc-wdm-iommu_map_logical_range_ex.md) with an explicit address provided on an [*IOMMU_DMA_DOMAIN** created with a BuddyAllocator will fail.

## -see-also

[IOMMU_DOMAIN_CREATE_EX](nc-wdm-iommu_domain_create_ex.md)

[IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE](ne-wdm-iommu_dma_logical_allocator_type.md)
