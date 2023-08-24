---
UID: NE:wdm._IOMMU_DMA_DOMAIN_TYPE
tech.root: kernel
title: IOMMU_DMA_DOMAIN_TYPE
ms.date: 08/17/2023
targetos: Windows
description: Describes the domain types that can be created and interacted with via the DMA_IOMMU_INTERFACE_EX.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_DOMAIN_TYPE
 - PIOMMU_DMA_DOMAIN_TYPE
 - IOMMU_DMA_DOMAIN_TYPE
f1_keywords:
 - _IOMMU_DMA_DOMAIN_TYPE
 - wdm/_IOMMU_DMA_DOMAIN_TYPE
 - PIOMMU_DMA_DOMAIN_TYPE
 - wdm/PIOMMU_DMA_DOMAIN_TYPE
 - IOMMU_DMA_DOMAIN_TYPE
 - wdm/IOMMU_DMA_DOMAIN_TYPE
dev_langs:
 - c++
---

## -description

Describes the domain types that can be created and interacted with via the [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md).

## -enum-fields

### -field DomainTypeTranslate

The standard remapping domain. The HAL/Hypervisor will create a domain structure and page table for holding logical address mappings.

### -field DomainTypePassThrough

Represents a passthrough domain. Calls to map and unmap are not necessary. Depending on the DMAGuard policy of the machine, this domain may not be available.

### -field DomainTypeUnmanaged

This is a remapping domain in which the page table is owned by the caller. The caller is responsible for interacting with the IOMMU Interface to provide its page table as well as performing necessary IOMMU TLB flushes.

### -field DomainTypeMax

Invalid domain type.

## -remarks

## -see-also

[**IOMMU_DOMAIN_CREATE_EX**](nc-wdm-iommu_domain_create_ex.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)
