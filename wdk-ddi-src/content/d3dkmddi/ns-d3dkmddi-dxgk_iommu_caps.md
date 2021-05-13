---
UID: NS:d3dkmddi._DXGK_IOMMU_CAPS
tech.root: display
title: DXGK_IOMMU_CAPS
ms.date: 05/13/2021
ms.topic: language-reference
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

Indicates that the driver supports IOMMU hardware and isolation. This field mimics [**DXGK_DRIVERCAPS.MemoryManagementCaps.IOMMUSecureModeSupported**](ns-d3dkmddi-_dxgk_vidmmcaps.md).

### -field IommuIsolationRequired

Indicates that IOMMU hardware and isolation support is required; otherwise, the OS will not start the adapter. This field mimics [**DXGK_DRIVERCAPS.MemoryManagementCaps.IOMMUSecureModeRequired**](ns-d3dkmddi-_dxgk_vidmmcaps.md).

### -field DmaRemappingSupported

Indicates that linear remapping is supported by the driver, and not just the 1:1 mappings used for standard isolation.

### -field Reserved

Reserved; do not use.

### -field Value

An alternative method to access the bits.

## -remarks

The driver fills in this structure when *Dxgkernel* calls [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) with a [**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) value of **DXGKQAITYPE_IOMMU_CAPS**.

To indicate logical DMA remapping support, the driver must also fill in [**DXGK_PHYSICAL_MEMORY_CAPS**](ns-d3dkmddi-dxgk_physical_memory_caps.md) accordingly.

## -see-also

[**DXGK_PHYSICAL_MEMORY_CAPS**](ns-d3dkmddi-dxgk_physical_memory_caps.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DXGK_VIDMMCAPS**](ns-d3dkmddi-_dxgk_vidmmcaps.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
