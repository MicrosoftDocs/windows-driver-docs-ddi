---
UID: NS:d3dkmddi._DXGK_IOMMU_CAPS
tech.root: display
title: DXGK_IOMMU_CAPS
ms.date: 06/24/2022
targetos: Windows
description: The DXGK_IOMMU_CAPS structure is used to indicate whether a driver supports IOMMU linear remapping.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXGK_IOMMU_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_IOMMU_CAPS
 - DXGK_IOMMU_CAPS
f1_keywords:
 - _DXGK_IOMMU_CAPS
 - d3dkmddi/_DXGK_IOMMU_CAPS
 - DXGK_IOMMU_CAPS
 - d3dkmddi/DXGK_IOMMU_CAPS
dev_langs:
 - c++
---

## -description

The **DXGK_IOMMU_CAPS** structure is used to indicate whether a driver supports IOMMU linear remapping.

## -struct-fields

### -field IommuIsolationSupported

Indicates that the driver supports IOMMU isolation, and fully utilizes the IOMMU callback API to map driver-allocated memory objects to the IOMMU domain. This field mimics [**DXGK_DRIVERCAPS.MemoryManagementCaps.IOMMUSecureModeSupported**](ns-d3dkmddi-_dxgk_vidmmcaps.md). *Dxgkrnl* expects these capabilities to match.

### -field IommuIsolationRequired

Indicates that the IOMMU is required for the hardware to function correctly and safely. If an IOMMU is not present on the system or a domain cannot be attached to the device, the device will not start. This field mimics [**DXGK_DRIVERCAPS.MemoryManagementCaps.IOMMUSecureModeRequired**](ns-d3dkmddi-_dxgk_vidmmcaps.md). *Dxgkrnl* expects these capabilities to match.

### -field DmaRemappingSupported

Indicates that linear remapping is supported by the driver, and not just the 1:1 mappings used for standard isolation. If multiple linked physical adapters have different values for their highest visible address, the driver should report the minimum value of all physical adapters.

### -field Reserved

Reserved; do not use.

### -field Value

An alternative method to access the bits.

## -remarks

The driver fills in this structure when *Dxgkrnl* calls [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) with a [**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) value of **DXGKQAITYPE_IOMMU_CAPS**. *Dxgkrnl* will call **DxgkDdiQueryAdapterInfo** after [**DxgkddiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) has been called for all physical adapters, but before [**DxgkddiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md). The driver is expected to know about all linked physical adapters at this time.

To indicate logical DMA remapping support, the driver must also fill in [**DXGK_PHYSICAL_MEMORY_CAPS**](ns-d3dkmddi-dxgk_physical_memory_caps.md) accordingly.

For more information, see [IOMMU DMA remapping](/windows-hardware/drivers/display/iommu-dma-remapping).

## -see-also

[**DXGK_PHYSICAL_MEMORY_CAPS**](ns-d3dkmddi-dxgk_physical_memory_caps.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DXGK_VIDMMCAPS**](ns-d3dkmddi-_dxgk_vidmmcaps.md)

[**DxgkddiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

 [**DxgkddiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
