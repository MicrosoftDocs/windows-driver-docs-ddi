---
UID: NS:wdm._IOMMU_DMA_RESERVED_REGION
tech.root: kernel
title: IOMMU_DMA_RESERVED_REGION
ms.date: 06/13/2021
targetos: Windows
description: The IOMMU_DMA_RESERVED_REGION structure describes a region of memory that needs to be marked as reserved during domain creation.
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
req.typenames: IOMMU_DMA_RESERVED_REGION, *PIOMMU_DMA_RESERVED_REGION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_RESERVED_REGION
 - PIOMMU_DMA_RESERVED_REGION
 - IOMMU_DMA_RESERVED_REGION
f1_keywords:
 - _IOMMU_DMA_RESERVED_REGION
 - wdm/_IOMMU_DMA_RESERVED_REGION
 - PIOMMU_DMA_RESERVED_REGION
 - wdm/PIOMMU_DMA_RESERVED_REGION
 - IOMMU_DMA_RESERVED_REGION
 - wdm/IOMMU_DMA_RESERVED_REGION
dev_langs:
 - c++
---

## -description

The **IOMMU_DMA_RESERVED_REGION** structure describes a region of memory that needs to be marked as reserved during domain creation. This structure is used by [*IOMMU_DOMAIN_CREATE_EX*](nc-wdm-iommu_domain_create_ex.md).

## -struct-fields

### -field RegionNext

Provides a pointer to the next reserved region.

### -field Base

Provides the base address of the region to be reserved. Must be page-aligned.

### -field NumberOfPages

Provides the number of pages to be reserved.

### -field ShouldMap

Provides whether the reserved region should be identity mapped. If not, the region will not be mapped into the domain's page table at all.

## -remarks

If the domain being created has a logical allocator, the logical address range will be marked as reserved within the logical allocator as well.

## -see-also

[IOMMU_DOMAIN_CREATE_EX](nc-wdm-iommu_domain_create_ex.md)
