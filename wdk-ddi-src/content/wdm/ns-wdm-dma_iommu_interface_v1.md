---
UID: NS:wdm._DMA_IOMMU_INTERFACE_V1
tech.root: kernel
title: DMA_IOMMU_INTERFACE_V1
ms.date: 04/20/2021
targetos: Windows
description: "Learn more about: DMA_IOMMU_INTERFACE_V1"
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
req.typenames: DMA_IOMMU_INTERFACE_V1, *PDMA_IOMMU_INTERFACE_V1
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_IOMMU_INTERFACE_V1
 - PDMA_IOMMU_INTERFACE_V1
 - DMA_IOMMU_INTERFACE_V1
f1_keywords:
 - _DMA_IOMMU_INTERFACE_V1
 - wdm/_DMA_IOMMU_INTERFACE_V1
 - PDMA_IOMMU_INTERFACE_V1
 - wdm/PDMA_IOMMU_INTERFACE_V1
 - DMA_IOMMU_INTERFACE_V1
 - wdm/DMA_IOMMU_INTERFACE_V1
dev_langs:
 - c++
---

## -description

A structure containing the set of IOMMU Version 1 (V1) functions.

## -struct-fields

### -field CreateDomain

A pointer to the [**IOMMU_DOMAIN_CREATE**](nc-wdm-iommu_domain_create.md) function that creates a DMA remapping device domain.

### -field DeleteDomain

A pointer to the [**IOMMU_DOMAIN_DELETE**](nc-wdm-iommu_domain_delete.md) function that deletes a device domain.

### -field AttachDevice

A pointer to the [**IOMMU_DOMAIN_ATTACH_DEVICE**](nc-wdm-iommu_domain_attach_device.md) function that attaches a device to a domain.

### -field DetachDevice

A pointer to the [**IOMMU_DOMAIN_ATTACH_DEVICE**](nc-wdm-iommu_domain_detach_device.md) function that detaches a device from a domain.

### -field FlushDomain

A pointer to the [**IOMMU_FLUSH_DOMAIN**](nc-wdm-iommu_flush_domain.md) function that flushes the TLB for all entries which match this domain.

### -field FlushDomainByVaList

A pointer to the [**IOMMU_FLUSH_DOMAIN_VA_LIST**](nc-wdm-iommu_flush_domain_va_list.md) function that flushes the TLB for all entries that match the specified domain's ASID and one of the addresses in the provided list.

### -field QueryInputMappings

A pointer to the [**IOMMU_QUERY_INPUT_MAPPINGS**](nc-wdm-iommu_query_input_mappings.md) function that attempts to find input mapping IDs which are valid for the given device and populate the provided buffer with those IDs.

### -field MapLogicalRange

A pointer to the [**IOMMU_MAP_LOGICAL_RANGE**](nc-wdm-iommu_map_logical_range.md) function that maps a range of pages into the address space of the specified domain.

### -field UnmapLogicalRange

A pointer to the [**IOMMU_UNMAP_LOGICAL_RANGE**](nc-wdm-iommu_unmap_logical_range.md) function that unmaps a range of pages.

### -field MapIdentityRange

A pointer to the [**IOMMU_MAP_IDENTITY_RANGE**](nc-wdm-iommu_map_identity_range.md) function that creates an identity mapping for the provided MDL in the specified domain.

### -field UnmapIdentityRange

A pointer to the [**IOMMU_UNMAP_IDENTITY_RANGE**](nc-wdm-iommu_unmap_identity_range.md) function that deletes an identity mapping.

### -field SetDeviceFaultReporting

A pointer to the [**IOMMU_SET_DEVICE_FAULT_REPORTING**](nc-wdm-iommu_set_device_fault_reporting.md) function that sets the device fault reporting state to device already attached to a domain.

### -field ConfigureDomain

A pointer to the [**IOMMU_DOMAIN_CONFIGURE**](nc-wdm-iommu_domain_configure.md) function that configures a domain for use.

## -remarks

These function pointers are the same as those provided by the deprecated [**DMA_IOMMU_INTERFACE**](ns-wdm-_dma_iommu_interface.md) structure. For V1 functions, use the [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) structure over the deprecated one.

## -see-also

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
