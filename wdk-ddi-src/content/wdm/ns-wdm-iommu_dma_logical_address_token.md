---
UID: NS:wdm._IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
tech.root: kernel
title: IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
ms.date: 06/04/2021
targetos: Windows
description: The IOMMU_DMA_LOGICAL_ADDRESS_TOKEN represents a reserved contiguous logical address range created by IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE.
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
req.typenames: IOMMU_DMA_LOGICAL_ADDRESS_TOKEN, *PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
f1_keywords:
 - _IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - wdm/_IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - wdm/PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
 - wdm/IOMMU_DMA_LOGICAL_ADDRESS_TOKEN
dev_langs:
 - c++
---

## -description

The **IOMMU_DMA_LOGICAL_ADDRESS_TOKEN** represents a reserved contiguous logical address range created by [IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_reserve_logical_address_range.md). Logical address tokens guarantee that the logical address represented has all of its associated page tables allocated ahead of time, ensuring that future mappings to this region will not fail due to low memory conditions.

## -struct-fields

### -field LogicalAddressBase

Represents the base address of the logical address range.

### -field Size

Represents the size, in bytes, of the logical address range.

## -remarks

Logical Address tokens can be created and freed via [IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_reserve_logical_address_range.md) and [IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_free_reserved_logical_address_range.md).

Logical Address tokens should have portions of their logical address ranges mapped to and unmapped from physical addresses via [IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md) and [IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md).

## -see-also

[IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_reserve_logical_address_range.md)

[IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_free_reserved_logical_address_range.md)

[IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md)

[IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md)

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT](./ns-wdm-iommu_dma_logical_address_token_mapped_segment.md)
