---
UID: NC:wdm.IOMMU_DOMAIN_CREATE_EX
tech.root: kernel
title: IOMMU_DOMAIN_CREATE_EX
ms.date: 06/09/2021
targetos: Windows
description: Creates a new DMA device domain based on the provided domain type.
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
 - IOMMU_DOMAIN_CREATE_EX
f1_keywords:
 - IOMMU_DOMAIN_CREATE_EX
 - wdm/IOMMU_DOMAIN_CREATE_EX
dev_langs:
 - c++
---

## -description

Creates a new DMA device domain based on the provided domain type.

## -parameters

### -param DomainType [in]


Indicates the type of domain to be created. See [**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md).

### -param Flags [in]


Configuration flags for the device domain. Currently unused and must be set to 0. See [**IOMMU_DMA_DOMAIN_CREATION_FLAGS**](ns-wdm-iommu_dma_domain_creation_flags.md).

### -param LogicalAllocatorConfig [in, optional]


Optionally provides a logical allocator configuration to initialize a HAL-implemented logical allocator to be associated with the domain. See [**IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG**](ns-wdm-iommu_dma_logical_allocator_config.md).

### -param ReservedRegions [in, optional]


Optionally provides a set of [**IOMMU_DMA_RESERVED_REGION**](ns-wdm-iommu_dma_reserved_region.md) structures to be reserved during domain creation.

### -param DomainOut [out]


Returns an opaque handle to the created domain.

## -returns

**STATUS_SUCCESS** if the operation is successful. Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| STATUS_INSUFFICIENT_RESOURCES | The routine failed to allocate resources required for the domain or there are not enough ASIDs for unmanaged domains. |
| STATUS_NOT_SUPPORTED | The hypervisor domain interface not available, x86 guest machine attempting to create a domain, or provided domain type is currently not allowed. |

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

To delete a domain created by **IOMMU_DOMAIN_CREATE_EX**, use [*IOMMU_DOMAIN_DELETE*](nc-wdm-iommu_domain_delete.md); there currently is no Ex equivalent of domain deletion.

## -see-also

[**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md)

[**IOMMU_DMA_DOMAIN_CREATION_FLAGS**](ns-wdm-iommu_dma_domain_creation_flags.md)

[**IOMMU_DMA_LOGICAL_ALLOCATOR_CONFIG**](ns-wdm-iommu_dma_logical_allocator_config.md)

[**IOMMU_DMA_RESERVED_REGION**](ns-wdm-iommu_dma_reserved_region.md)

[*IOMMU_DOMAIN_DELETE*](nc-wdm-iommu_domain_delete.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
