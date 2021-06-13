---
UID: NE:wdm._IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
tech.root: kernel
title: IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
ms.date: 05/27/2021
targetos: Windows
description: The IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE enum indicates the type of logical allocator described in an IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG structure.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - PIOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
f1_keywords:
 - _IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - wdm/_IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - PIOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - wdm/PIOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
 - wdm/IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE
dev_langs:
 - c++
---

## -description

The **IOMMU_DMA_LOGICAL_ALLOCATOR_TYPE** enum indicates the type of logical allocator described in an [**IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG**](ns-wdm-iommu_dma_logical_allocator_config.md) structure.

## -enum-fields

### -field IommuDmaLogicalAllocatorNone

The logical allocator configuration does not describe any logical allocator type.

### -field IommuDmaLogicalAllocatorBuddy

The logical allocator configuration describes the system's Buddy Allocator.

### -field IommuDmaLogicalAllocatorMax

Invalid logical allocator type.

## -remarks

For more information about the different logical allocator types available, see the Remarks section of [**IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG**](ns-wdm-iommu_dma_logical_allocator_config.md).

## -see-also

[IOMMU_DOMAIN_CREATE_EX](nc-wdm-iommu_domain_create_ex.md)

[IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG](ns-wdm-iommu_dma_logical_allocator_config.md)
