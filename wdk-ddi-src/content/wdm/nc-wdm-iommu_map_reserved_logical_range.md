---
UID: NC:wdm.IOMMU_MAP_RESERVED_LOGICAL_RANGE
tech.root: kernel
title: IOMMU_MAP_RESERVED_LOGICAL_RANGE
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
 - IOMMU_MAP_RESERVED_LOGICAL_RANGE
f1_keywords:
 - IOMMU_MAP_RESERVED_LOGICAL_RANGE
 - wdm/IOMMU_MAP_RESERVED_LOGICAL_RANGE
dev_langs:
 - c++
---

## -description

Maps a reserved logical range. Unlike [**IOMMU_MAP_LOGICAL_RANGE_EX**](./nc-wdm-iommu_map_logical_range_ex.md), this is guaranteed not to perform any memory allocations as they are assumed to have already been performed earlier with [**IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE**](./nc-wdm-iommu_reserve_logical_address_range.md).

## -parameters

### -param LogicalAddressToken

[*Inout*] The [**IOMMU_DMA_LOGICAL_ADDRESS_TOKEN**](./ns-wdm-iommu_dma_logical_address_token.md) to be mapped to.

### -param Offset

[*In*] The offset, in bytes, into the logical address token, representing the base logical address to be mapped.

### -param Permissions

[*In*] A bit-field representing the permissions to be set for the range being mapped. See Remarks for the available permission bits.

### -param PhysicalAddressToMap

[*In*] The [**IOMMU_MAP_PHYSICAL_ADDRESS**](./ns-wdm-iommu_map_physical_address.md) that will be mapped to the domain.

### -param MappedSegment

[*Out*] Returns the [**IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT**](./ns-wdm-iommu_dma_logical_address_token_mapped_segment.md) representing a segment of the logical address token that is now mapped.

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
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The offset provided is not page aligned.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The physical address provided is not page aligned and/or is not a whole number of pages in size.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The logical address range represented in the logical address token is already completely or partially mapped.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The logical address token is currently being deleted.
</td>
</tr>

</table>

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

A logical address token mapped segment can be unmapped via [**IOMMU_UNMAP_RESERVED_LOGICAL_RANGE**](./nc-wdm-iommu_unmap_reserved_logical_range.md).

The permissions field is a bitfield that describes the access permissions for the pages to be mapped. The bits are defined as follows:
*Bit 0 = Read Access*

*Bit 1 = Write Access*

*Bits 31-2 = Reserved (0)*

## -see-also

[IOMMU_UNMAP_RESERVED_LOGICAL_RANGE](./nc-wdm-iommu_unmap_reserved_logical_range.md)

[IOMMU_MAP_PHYSICAL_ADDRESS](./ns-wdm-iommu_map_physical_address.md)

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN](./ns-wdm-iommu_dma_logical_address_token.md)

[IOMMU_DMA_LOGICAL_ADDRESS_TOKEN_MAPPED_SEGMENT](./ns-wdm-iommu_dma_logical_address_token_mapped_segment.md)