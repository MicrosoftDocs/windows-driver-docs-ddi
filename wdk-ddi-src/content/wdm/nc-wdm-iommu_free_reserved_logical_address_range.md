---
UID: NC:wdm.IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE
tech.root: kernel
title: IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE
ms.date: 05/27/2021
targetos: Windows
description: TBD
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
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
 - IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE
f1_keywords:
 - IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE
 - wdm/IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE
dev_langs:
 - c++
---

## -description

Frees a logical address token created by [**IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE**](./nc-wdm-iommu_reserve_logical_address_range.md).

## -parameters

### -param LogicalAddressToken

[*In*] The [**IOMMU_DMA_LOGICAL_ADDRESS_TOKEN**](./ns-wdm-iommu_dma_logical_address_token.md), representing the reserved logical address range, to be freed.

## -returns

**STATUS_SUCCESS** if the operation is successful.

**STATUS_RESOURCE_IN_USE** if the logical address range is currently mapped or partially mapped.

## -remarks

Before deleting an **IOMMU_DMA_DOMAIN**, all associated logical address tokens must be freed.

## -see-also

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md)

[IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_reserve_logical_address_range.md)

[IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md)

[IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md)