---
UID: NC:wdm.IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE
tech.root: kernel
title: IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE
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
 - IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE
f1_keywords:
 - IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE
 - wdm/IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE
dev_langs:
 - c++
---

## -description

Preallocates logical address space that can be used for future mappings. This grants a driver the ability to ensure forward progress for future map/unmap calls.

## -parameters

### -param Domain

[*In*] A pointer to the **IOMMU_DMA_DOMAIN** that the reserved logical address will belong to. The domain must be of type *DomainTypeTranslate*. For more information about domain types, see [IOMMU_DMA_DOMAIN_TYPE](./ne-wdm-iommu_dma_domain_type.md).

### -param Size

[*In*] The size, in bytes, of the logical address range to reserve. This value must represent a whole number of pages.

### -param ExplicitLogicalAddress

[*In, Optional*] The domain logical address that should be reserved. If the domain was not created with a registered logical allocator, then this field is required. If the domain was created with a registered logical allocator that does not support explicit logical address allocation, then this field must be *NULL*.

### -param MinLogicalAddress

[*In, Optional*] The minimum (inclusive) allowable logical address that can be reserved. If the domain was not created with a registered logical allocator, then this field will be ignored.

### -param MaxLogicalAddress

[*In, Optional*] The maximum (inclusive) allowable logical address that can be reserved. If the domain was not created with a registered logical allocator, then this field will be ignored.

### -param LogicalAddressToken

[*Out*] Returns a [**IOMMU_DMA_LOGICAL_ADDRESS_TOKEN**](./ns-wdm-iommu_dma_logical_address_token.md) representing the reserved logical address range.

## -returns

**STATUS_SUCCESS** if the operation is successful. Possible error return values include the following status codes.

<table>

<tr>
<th>Return code</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The domain provided is not of type <i>DomainTypeTranslate</i>.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The size provided is not a multiple of PAGE_SIZE.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The ExplicitLogicalAddress provided is not page-aligned.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_MIX</b></dt>
</dl>
</td>
<td width="60%">
The min and max logical addresses provided could not be satisfied.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The ExplicitLogicalAddress is already mapped or partially mapped.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
An ExplicitLogicalAddress was provided for a domain with a logical allocator that does not allow explicit logical address allocation. Or an ExplicitLogicalAddress was not provided for a domain with no logical allocator.
</td>
</tr>

</table>

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Logical Address tokens can be freed via [IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_free_reserved_logical_address_range.md).

Logical Address tokens should have portions of their logical address ranges mapped to and unmapped from physical addresses via [IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md) and [IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md).

## -see-also

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md)

[IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE](./nc-wdm-iommu_free_reserved_logical_address_range.md)

[IOMMU_MAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_map_reserved_logical_range.md)

[IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md)