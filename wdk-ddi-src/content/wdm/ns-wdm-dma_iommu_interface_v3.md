---
UID: NS:wdm._DMA_IOMMU_INTERFACE_V3
tech.root: kernel
title: DMA_IOMMU_INTERFACE_V3 (wdm.h)
ms.date: 10/04/2022
targetos: Windows
description: Describes the DMA_IOMMU_INTERFACE_V3 (wdm.h) structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: DMA_IOMMU_INTERFACE_V3, *PDMA_IOMMU_INTERFACE_V3
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DMA_IOMMU_INTERFACE_V3
 - PDMA_IOMMU_INTERFACE_V3
 - DMA_IOMMU_INTERFACE_V3
f1_keywords:
 - _DMA_IOMMU_INTERFACE_V3
 - wdm/_DMA_IOMMU_INTERFACE_V3
 - PDMA_IOMMU_INTERFACE_V3
 - wdm/PDMA_IOMMU_INTERFACE_V3
 - DMA_IOMMU_INTERFACE_V3
 - wdm/DMA_IOMMU_INTERFACE_V3
dev_langs:
 - c++
helpviewer_keywords:
 - _DMA_IOMMU_INTERFACE_V3
---

## -description

Describes the **DMA_IOMMU_INTERFACE_V3** structure.

## -struct-fields

### -field CreateDomainEx

Defines the **PIOMMU_DOMAIN_CREATE_EX** member **CreateDomainEx**.

### -field DeleteDomain

Defines the **PIOMMU_DOMAIN_DELETE** member **DeleteDomain**.

### -field AttachDeviceEx

Defines the **PIOMMU_DOMAIN_ATTACH_DEVICE_EX** member **AttachDeviceEx**.

### -field DetachDeviceEx

Defines the **PIOMMU_DOMAIN_DETACH_DEVICE_EX** member **DetachDeviceEx**.

### -field FlushDomain

Defines the **PIOMMU_FLUSH_DOMAIN** member **FlushDomain**.

### -field FlushDomainByVaList

Defines the **PIOMMU_FLUSH_DOMAIN_VA_LIST** member **FlushDomainByVaList**.

### -field QueryInputMappings

Defines the **PIOMMU_QUERY_INPUT_MAPPINGS** member **QueryInputMappings**.

### -field MapLogicalRangeEx

Defines the **PIOMMU_MAP_LOGICAL_RANGE_EX** member **MapLogicalRangeEx**.

### -field UnmapLogicalRange

Defines the **PIOMMU_UNMAP_LOGICAL_RANGE** member **UnmapLogicalRange**.

### -field MapIdentityRangeEx

Defines the **PIOMMU_MAP_IDENTITY_RANGE_EX** member **MapIdentityRangeEx**.

### -field UnmapIdentityRangeEx

Defines the **PIOMMU_UNMAP_IDENTITY_RANGE_EX** member **UnmapIdentityRangeEx**.

### -field SetDeviceFaultReportingEx

Defines the **PIOMMU_SET_DEVICE_FAULT_REPORTING_EX** member **SetDeviceFaultReportingEx**.

### -field ConfigureDomain

Defines the **PIOMMU_DOMAIN_CONFIGURE** member **ConfigureDomain**.

### -field QueryAvailableDomainTypes

Defines the **PIOMMU_DEVICE_QUERY_DOMAIN_TYPES** member **QueryAvailableDomainTypes**.

### -field RegisterInterfaceStateChangeCallback

Defines the **PIOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK** member **RegisterInterfaceStateChangeCallback**.

### -field UnregisterInterfaceStateChangeCallback

Defines the **PIOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK** member **UnregisterInterfaceStateChangeCallback**.

### -field ReserveLogicalAddressRange

Defines the **PIOMMU_RESERVE_LOGICAL_ADDRESS_RANGE** member **ReserveLogicalAddressRange**.

### -field FreeReservedLogicalAddressRange

Defines the **PIOMMU_FREE_RESERVED_LOGICAL_ADDRESS_RANGE** member **FreeReservedLogicalAddressRange**.

### -field MapReservedLogicalRange

Defines the **PIOMMU_MAP_RESERVED_LOGICAL_RANGE** member **MapReservedLogicalRange**.

### -field UnmapReservedLogicalRange

Defines the **PIOMMU_UNMAP_RESERVED_LOGICAL_RANGE** member **UnmapReservedLogicalRange**.

### -field CreateDevice

Defines the **PIOMMU_DEVICE_CREATE** member **CreateDevice**.

### -field DeleteDevice

Defines the **PIOMMU_DEVICE_DELETE** member **DeleteDevice**.

### -field CreatePasidDevice

Defines the **PIOMMU_PASID_DEVICE_CREATE** member **CreatePasidDevice**.

### -field DeletePasidDevice

Defines the **PIOMMU_PASID_DEVICE_DELETE** member **DeletePasidDevice**.

### -field AttachPasidDevice

Defines the **PIOMMU_DOMAIN_ATTACH_PASID_DEVICE** member **AttachPasidDevice**.

### -field DetachPasidDevice

Defines the **PIOMMU_DOMAIN_DETACH_PASID_DEVICE** member **DetachPasidDevice**.

### -field QueryDeviceInfo

Defines the **PIOMMU_DEVICE_QUERY_INFORMATION** member **QueryDeviceInfo**.

## -remarks

## -see-also
