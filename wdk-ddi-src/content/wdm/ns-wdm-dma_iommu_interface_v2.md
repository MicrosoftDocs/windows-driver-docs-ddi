---
UID: NS:wdm._DMA_IOMMU_INTERFACE_V2
tech.root: kernel
title: DMA_IOMMU_INTERFACE_V2
ms.date: 06/09/2021
targetos: Windows
description: A structure containing the set of IOMMU Version 2 (V2) functions.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DMA_IOMMU_INTERFACE_V2, *PDMA_IOMMU_INTERFACE_V2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_IOMMU_INTERFACE_V2
 - PDMA_IOMMU_INTERFACE_V2
 - DMA_IOMMU_INTERFACE_V2
f1_keywords:
 - _DMA_IOMMU_INTERFACE_V2
 - wdm/_DMA_IOMMU_INTERFACE_V2
 - PDMA_IOMMU_INTERFACE_V2
 - wdm/PDMA_IOMMU_INTERFACE_V2
 - DMA_IOMMU_INTERFACE_V2
 - wdm/DMA_IOMMU_INTERFACE_V2
dev_langs:
 - c++
---

## -description

A structure containing the set of IOMMU Version 2 (V2) functions.

## -struct-fields

### -field CreateDomainEx

A pointer to the [**IOMMU_DOMAIN_CREATE_EX**](nc-wdm-iommu_domain_create_ex.md) function that creates a DMA remapping device domain.

### -field DeleteDomain

A pointer to the [**IOMMU_DOMAIN_DELETE**](nc-wdm-iommu_domain_delete.md) function that deletes a device domain.

### -field AttachDeviceEx

A pointer to the [**IOMMU_DOMAIN_ATTACH_DEVICE_EX**](nc-wdm-iommu_domain_attach_device_ex.md) function that attaches a device to a domain.

### -field DetachDeviceEx

A pointer to the [**IOMMU_DOMAIN_DETACH_DEVICE_EX**](nc-wdm-iommu_domain_detach_device_ex.md) function that detaches a device from a domain.

### -field FlushDomain

A pointer to the [**IOMMU_FLUSH_DOMAIN**](nc-wdm-iommu_flush_domain.md) function that flushes the TLB for all entries which match this domain.

### -field FlushDomainByVaList

A pointer to the [**IOMMU_FLUSH_DOMAIN_VA_LIST**](nc-wdm-iommu_flush_domain_va_list.md) function that flushes the TLB for all entries that match the specified domain's ASID and one of the addresses in the provided list.

### -field QueryInputMappings

A pointer to the [**IOMMU_QUERY_INPUT_MAPPINGS**](nc-wdm-iommu_query_input_mappings.md) function that attempts to find input mapping IDs which are valid for the given device and populate the provided buffer with those IDs.

### -field MapLogicalRangeEx

A pointer to the [**IOMMU_MAP_LOGICAL_RANGE_EX**](nc-wdm-iommu_map_logical_range_ex.md) function that maps a range of pages into the address space of the specified domain.

### -field UnmapLogicalRange

A pointer to the [**IOMMU_UNMAP_LOGICAL_RANGE**](nc-wdm-iommu_unmap_logical_range.md) function that unmaps a range of pages.

### -field MapIdentityRangeEx

A pointer to the [**IOMMU_MAP_IDENTITY_RANGE_EX**](nc-wdm-iommu_map_identity_range_ex.md) function that creates an identity mapping for the provided physical address in the provided domain.

### -field UnmapIdentityRangeEx

A pointer to the [**IOMMU_UNMAP_IDENTITY_RANGE_EX**](nc-wdm-iommu_unmap_identity_range_ex.md) function that deletes an identity mapping for the specified physical address.

### -field SetDeviceFaultReportingEx

A pointer to the [**IOMMU_SET_DEVICE_FAULT_REPORTING_EX**](nc-wdm-iommu_set_device_fault_reporting_ex.md) function that sets the device fault reporting state on a device already attached to a domain.

### -field ConfigureDomain

A pointer to the [**IOMMU_DOMAIN_CONFIGURE**](nc-wdm-iommu_domain_configure.md) function that configures a domain for use.

### -field QueryAvailableDomainTypes

A pointer to the [**IOMMU_DEVICE_QUERY_DOMAIN_TYPES**](nc-wdm-iommu_device_query_domain_types.md) function that queries for the available types of domains that a device is allowed to attach to, depending on environment factors, such as platform and the DMA Guard policy.

### -field RegisterInterfaceStateChangeCallback

A pointer to the [**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md) function that allows the caller to register a callback to be invoked whenever any state change related to the IOMMU interface occurs.

### -field UnregisterInterfaceStateChangeCallback

A pointer to the [**IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_unregister_interface_state_change_callback.md) function that allows the caller to deregister a registered callback.

### -field ReserveLogicalAddressRange

A pointer to the [**IOMMU_RESERVE_LOGICAL_ADDRESS_RANGE**](nc-wdm-iommu_reserve_logical_address_range.md) function that preallocates logical address space that can be used for future mappings.

### -field FreeReservedLogicalAddressRange

A pointer to the [**IOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE**](nc-wdm-iommu_free_reserved_logical_address_range.md) function that frees a logical address token.

### -field MapReservedLogicalRange

A pointer to the [**IOMMU_MAP_RESERVED_LOGICAL_RANGE**](nc-wdm-iommu_map_reserved_logical_range.md) function that maps a reserved logical range.

### -field UnmapReservedLogicalRange

A pointer to the [**IOMMU_UNMAP_RESERVED_LOGICAL_RANGE**](nc-wdm-iommu_unmap_reserved_logical_range.md) function that unmaps a previously mapped reserved logical range.

### -field CreateDevice

A pointer to the [**IOMMU_DEVICE_CREATE**](nc-wdm-iommu_device_create.md) function that takes a physical device object and creates an **IOMMU_DMA_DEVICE**.

### -field DeleteDevice

A pointer to the [**IOMMU_DEVICE_DELETE**](nc-wdm-iommu_device_delete.md) function that deletes an **IOMMU_DMA_DEVICE**.

## -remarks

## -see-also

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
