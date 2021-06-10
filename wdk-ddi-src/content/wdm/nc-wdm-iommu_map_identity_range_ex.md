---
UID: NC:wdm.IOMMU_MAP_IDENTITY_RANGE_EX
tech.root: kernel
title: IOMMU_MAP_IDENTITY_RANGE_EX
ms.date: 06/09/2021
targetos: Windows
description: Creates an identity mapping for a provided physical address space in the provided domain.
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
 - IOMMU_MAP_IDENTITY_RANGE_EX
f1_keywords:
 - IOMMU_MAP_IDENTITY_RANGE_EX
 - wdm/IOMMU_MAP_IDENTITY_RANGE_EX
dev_langs:
 - c++
---

## -description

Creates an identity mapping for a provided physical address space in the provided domain.

## -parameters

### -param Domain

[in]
A pointer to the **IOMMU_DMA_DOMAIN** that the identity mapped physical address will belong to. The domain must be of type *DomainTypeTranslate* or *DomainTypePassThrough*. For more information about domain types, see [IOMMU_DMA_DOMAIN_TYPE](ne-wdm-iommu_dma_domain_type.md).

### -param Permissions

[in]
A bit-field representing the permissions to be set for the range being mapped. See Remarks for the available permission bits.

### -param PhysicalAddressToMap

[in]
The [**IOMMU_MAP_PHYSICAL_ADDRESS**](ns-wdm-iommu_map_physical_address.md) that will be mapped to the domain.

## -returns

**STATUS_SUCCESS** if the operation is successful. Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| STATUS_INVALID_PARAMETER_1 | The domain provided is not of type *DomainTypeTranslate* or *DomainTypePassThrough*. |
| STATUS_INVALID_PARAMETER_3 | The [**IOMMU_MAP_PHYSICAL_ADDRESS**](ns-wdm-iommu_map_physical_address.md) provided does not represent physical memory that is page-aligned and has a size that is a multiple of PAGE_SIZE. |
| STATUS_IN_USE | The identity range is already mapped or partially mapped. |
| STATUS_NOT_SUPPORTED | The provided domain contains a logical allocator that does not allow explicit logical address allocation. |

## -remarks

To unmap the logical address created by **IOMMU_MAP_IDENTITY_RANGE_EX**, use [*IOMMU_UNMAP_IDENTITY_RANGE_EX*](nc-wdm-iommu_unmap_identity_range_ex.md).

The permissions field is a bitfield that describes the access permissions for the pages to be mapped.

The bits are defined as follows:

`Bit 0 = Read Access`

`Bit 1 = Write Access`

`Bits 31-2 = Reserved (0)`

## -see-also

[**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)

[**IOMMU_MAP_PHYSICAL_ADDRESS**](ns-wdm-iommu_map_physical_address.md)
