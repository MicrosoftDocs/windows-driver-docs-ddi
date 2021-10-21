---
UID: NC:wdm.IOMMU_MAP_LOGICAL_RANGE_EX
tech.root: kernel
title: IOMMU_MAP_LOGICAL_RANGE_EX
ms.date: 06/09/2021
targetos: Windows
description: Maps physical address space into the logical address space of an **IOMMU_DMA_DOMAIN**.
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
 - IOMMU_MAP_LOGICAL_RANGE_EX
f1_keywords:
 - IOMMU_MAP_LOGICAL_RANGE_EX
 - wdm/IOMMU_MAP_LOGICAL_RANGE_EX
dev_langs:
 - c++
---

## -description

Maps physical address space into the logical address space of an **IOMMU_DMA_DOMAIN**.

## -parameters

### -param Domain [in]


A pointer to the **IOMMU_DMA_DOMAIN** that the mapped logical address will belong to. The domain must be of type *DomainTypeTranslate*. For more information about domain types, see [IOMMU_DMA_DOMAIN_TYPE](ne-wdm-iommu_dma_domain_type.md).

### -param Permissions [in]


A bit-field representing the permissions to be set for the range being mapped. See Remarks for the available permission bits.

### -param PhysicalAddressToMap [in]


The [**IOMMU_MAP_PHYSICAL_ADDRESS**](ns-wdm-iommu_map_physical_address.md) that will be mapped to the domain.

### -param ExplicitLogicalAddress [in, optional]


The domain logical address that the physical address should be mapped to. If the domain was not created with a registered logical allocator, then this field is required. If the domain was created with a registered logical allocator that does not support explicit logical address allocation, then this field must be *NULL*.

### -param MinLogicalAddress [in, optional]


The minimum (inclusive) allowable logical address that the physical address should be mapped to. If the domain was not created with a registered logical allocator, then this field will be ignored.

### -param MaxLogicalAddress [in, optional]


The maximum (inclusive) allowable logical address that the physical address should be mapped to. If the domain was not created with a registered logical allocator, then this field will be ignored.

### -param LogicalAddressOut [out]


Returns the resulting logical address from the mapping.

## -returns

**STATUS_SUCCESS** if the operation is successful. Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| STATUS_INVALID_PARAMETER_1 | The domain provided is not of type *DomainTypeTranslate*. |
| STATUS_INVALID_PARAMETER_3 | The [**IOMMU_MAP_PHYSICAL_ADDRESS**](ns-wdm-iommu_map_physical_address.md) provided does not represent physical memory that is page-aligned and has a size that is a multiple of PAGE_SIZE. |
| STATUS_INVALID_PARAMETER_4 | The ExplicitLogicalAddress provided is not page-aligned. |
| STATUS_INVALID_PARAMETER_MIX | The min and max logical addresses provided could not be satisfied. |
| STATUS_IN_USE | The ExplicitLogicalAddress is already mapped or partially mapped. |
| STATUS_NOT_SUPPORTED | An ExplicitLogicalAddress was provided for a domain with a logical allocator that does not allow explicit logical address allocation. Or an ExplicitLogicalAddress was not provided for a domain with no logical allocator. |

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

To unmap the logical address created by **IOMMU_MAP_LOGICAL_RANGE_EX**, use [*IOMMU_UNMAP_LOGICAL_RANGE*](nc-wdm-iommu_unmap_logical_range.md); there currently is no Ex equivalent for logical address range unmapping.

The permissions field is a bitfield that describes the access permissions for the pages to be mapped.

The bits are defined as follows:

`Bit 0 = Read Access`

`Bit 1 = Write Access`

`Bits 31-2 = Reserved (0)`

## -see-also

[IOMMU_DMA_DOMAIN_TYPE](ne-wdm-iommu_dma_domain_type.md)

[IOMMU_MAP_PHYSICAL_ADDRESS](ns-wdm-iommu_map_physical_address.md)

[DMA_IOMMU_INTERFACE_V2](ns-wdm-dma_iommu_interface_v2.md)

[DMA_IOMMU_INTERFACE_EX](ns-wdm-dma_iommu_interface_ex.md)
