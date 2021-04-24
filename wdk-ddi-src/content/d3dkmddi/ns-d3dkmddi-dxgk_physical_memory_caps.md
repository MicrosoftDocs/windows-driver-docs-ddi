---
UID: NS:d3dkmddi._DXGK_PHYSICAL_MEMORY_CAPS
tech.root: display
title: DXGK_PHYSICAL_MEMORY_CAPS
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DXGK_PHYSICAL_MEMORY_CAPS structure provides information about the driver's physical memory restrictions.
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
req.typenames: DXGK_PHYSICAL_MEMORY_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_PHYSICAL_MEMORY_CAPS
 - DXGK_PHYSICAL_MEMORY_CAPS
f1_keywords:
 - _DXGK_PHYSICAL_MEMORY_CAPS
 - d3dkmddi/_DXGK_PHYSICAL_MEMORY_CAPS
 - DXGK_PHYSICAL_MEMORY_CAPS
 - d3dkmddi/DXGK_PHYSICAL_MEMORY_CAPS
dev_langs:
 - c++
---

## -description

The **DXGK_PHYSICAL_MEMORY_CAPS** structure provides information about the driver's physical memory restrictions.

## -struct-fields

### -field HighestVisibleAddress

The highest visible physical memory address. If multiple linked physical adapters have different values for their highest visible address, the driver should report the minimum value of all physical adapters.

## -remarks

The driver fills in this structure when *Dxgkernel* calls [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-DxgkDdiQueryAdapterInfo.md) with a [**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) value of **DXGKQAITYPE_PHYSICAL_MEMORY_CAPS**.

To indicate logical DMA remapping support, the driver must also fill in [**DXGK_IOMMU_CAPS**](ns-d3dkmddi-dxgk_iommu_caps.md) accordingly.

## -see-also

[**DXGK_IOMMU_CAPS**](ns-d3dkmddi-dxgk_iommu_caps.md)

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DXGK_VIDMMCAPS**](ns-d3dkmddi-_dxgk_vidmmcaps.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-DxgkDdiQueryAdapterInfo.md)
