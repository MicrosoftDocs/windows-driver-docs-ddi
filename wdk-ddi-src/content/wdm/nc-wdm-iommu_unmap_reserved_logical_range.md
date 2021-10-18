---
UID: NC:wdm.IOMMU_UNMAP_RESERVED_LOGICAL_RANGE
tech.root: kernel
title: IOMMU_UNMAP_RESERVED_LOGICAL_RANGE
ms.date: 06/09/2021
targetos: Windows
description: Unmaps a previously mapped reserved logical range.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdm.h
api_name:
 - IOMMU_UNMAP_RESERVED_LOGICAL_RANGE
f1_keywords:
 - IOMMU_UNMAP_RESERVED_LOGICAL_RANGE
 - wdm/IOMMU_UNMAP_RESERVED_LOGICAL_RANGE
dev_langs:
 - c++
---

## -description

Unmaps a previously mapped reserved logical range. Unlike [**IOMMU_UNMAP_LOGICAL_RANGE**](nc-wdm-iommu_unmap_logical_range.md), this is guaranteed not to delete any page table resources so that the logical address range can be reused without performing any memory allocations.

## -parameters

### -param MappedSegment

[in, out]
The [**IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT**](ns-wdm-iommu_dma_logical_address_token_mapped_segment.md) to be unmapped.

## -returns

**STATUS_SUCCESS** if the operation is successful.

**STATUS_INVALID_PARAMETER** if the mapped segment provided was not mapped.

## -remarks

## -see-also

[IOMMU_MAP_RESERVED_LOGICAL_RANGE](nc-wdm-iommu_map_reserved_logical_range.md)

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT](ns-wdm-iommu_dma_logical_address_token_mapped_segment.md)
