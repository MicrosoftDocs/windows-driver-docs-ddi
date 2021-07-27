---
UID: NS:wdm._IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
tech.root: kernel
title: IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
ms.date: 04/20/2021
targetos: Windows
description: "Learn more about: IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT"
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT, *PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
f1_keywords:
 - _IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - wdm/_IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - wdm/PIOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
 - wdm/IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT
dev_langs:
 - c++
---

## -description

The **IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT** represents a mapped portion of an [**IOMMU_DMA_LOGICAL_ADDRESS_TOKEN**](./ns-wdm-iommu_dma_logical_address_token.md).

## -struct-fields

### -field OwningToken

Provides a pointer to the logical address token that this mapped segment belongs to.

### -field Offset

The offset, in bytes, into the logical address token of the mapped region.

### -field Size

The size, in bytes, of the mapped region within the logical address token.

## -remarks

A **IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT** is initialized when calling [IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md) on an [IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md). It is invalidated when calling [IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md).

A segment must represent a 4KB page aligned range within an [IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md).

It is possible to map multiple segments within an [IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md) as long as the segments are not overlapping each other.

## -see-also

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md)

[IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md)

[IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md)
