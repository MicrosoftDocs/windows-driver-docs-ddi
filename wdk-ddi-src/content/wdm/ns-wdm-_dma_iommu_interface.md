---
UID: NS:wdm._DMA_IOMMU_INTERFACE
title: DMA_IOMMU_INTERFACE (wdm.h)
description: An extended version of the INTERFACE structure that allows device drivers to invoke the callback functions that perform device domain operations.
tech.root: kernel
ms.date: 01/06/2023
keywords: ["DMA_IOMMU_INTERFACE structure"]
ms.keywords: _DMA_IOMMU_INTERFACE, *PDMA_IOMMU_INTERFACE, DMA_IOMMU_INTERFACE,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DMA_IOMMU_INTERFACE, *PDMA_IOMMU_INTERFACE
targetos: Windows
f1_keywords:
 - _DMA_IOMMU_INTERFACE
 - wdm/_DMA_IOMMU_INTERFACE
 - PDMA_IOMMU_INTERFACE
 - wdm/PDMA_IOMMU_INTERFACE
 - DMA_IOMMU_INTERFACE
 - wdm/DMA_IOMMU_INTERFACE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_IOMMU_INTERFACE
 - PDMA_IOMMU_INTERFACE
 - DMA_IOMMU_INTERFACE
---

## -description

An extended version of the **INTERFACE** structure that allows device drivers to invoke the callback functions that perform device domain operations.

> [!CAUTION]
> `DMA_IOMMU_INTERFACE` has been deprecated in Windows 10, version 2103 and has been replaced by [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md).

## -struct-fields

### -field Version

The driver-defined interface version.

### -field CreateDomain

A pointer to the [**IOMMU_DOMAIN_CREATE**](nc-wdm-iommu_domain_create.md) callback function that creates a DMA remapping device domain.

### -field DeleteDomain

A pointer to the [**IOMMU_DOMAIN_DELETE**](nc-wdm-iommu_domain_delete.md) callback function that deletes a device domain.

### -field AttachDevice

A pointer to the [**IOMMU_DOMAIN_ATTACH_DEVICE**](nc-wdm-iommu_domain_attach_device.md) callback function that attaches a device to a domain.

### -field DetachDevice

A pointer to the [**IOMMU_DOMAIN_DETACH_DEVICE**](nc-wdm-iommu_domain_detach_device.md) callback function that detaches a device from a domain.

### -field ConfigureDomain

A pointer to the [**IOMMU_DOMAIN_CONFIGURE**](nc-wdm-iommu_domain_configure.md) callback function that configures a domain for use.

### -field FlushDomain

A pointer to the [**IOMMU_FLUSH_DOMAIN**](nc-wdm-iommu_flush_domain.md) callback function that flushes the TLB for all entries which match this domain.

### -field FlushDomainByVaList

A pointer to the [**IOMMU_FLUSH_DOMAIN_VA_LIST**](nc-wdm-iommu_flush_domain_va_list.md) callback function that flushes the TLB for all entries that match the specified domain's ASID and one of the addresses in the provided list.

### -field QueryInputMappings

A pointer to the [**IOMMU_QUERY_INPUT_MAPPINGS**](nc-wdm-iommu_query_input_mappings.md) callback function that attempts to find input mapping IDs which are valid for the given device and populate the provided buffer with those IDs.

### -field MapLogicalRange

A pointer to the [**IOMMU_MAP_LOGICAL_RANGE**](nc-wdm-iommu_map_logical_range.md) callback function that maps a range of pages into the address space of the specified domain.

### -field UnmapLogicalRange

A pointer to the [**IOMMU_UNMAP_LOGICAL_RANGE**](nc-wdm-iommu_unmap_logical_range.md) callback function that unmaps a range of pages.

### -field MapIdentityRange

A pointer to the [**IOMMU_MAP_IDENTITY_RANGE**](nc-wdm-iommu_map_identity_range.md) callback function that creates an identity mapping for the provided MDL in the specified domain.

### -field UnmapIdentityRange

A pointer to the [**IOMMU_UNMAP_IDENTITY_RANGE**](nc-wdm-iommu_unmap_identity_range.md) callback function that deletes an identity mapping.

### -field SetDeviceFaultReporting

A pointer to the [**IOMMU_SET_DEVICE_FAULT_REPORTING**](nc-wdm-iommu_set_device_fault_reporting.md) callback function that sets the device fault reporting state to device already attached to a domain.

## -remarks

## -see-also
