---
UID: NS:wdm._IOMMU_DMA_DEVICE_INFORMATION
tech.root: kernel
title: IOMMU_DMA_DEVICE_INFORMATION
ms.date: 08/07/2025
targetos: Windows
description: Contains information about an IOMMU DMA device's PASID capabilities and configuration. 
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
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: IOMMU_DMA_DEVICE_INFORMATION, *PIOMMU_DMA_DEVICE_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ai-usage: ai-assisted 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_DEVICE_INFORMATION
 - PIOMMU_DMA_DEVICE_INFORMATION
 - IOMMU_DMA_DEVICE_INFORMATION
f1_keywords:
 - _IOMMU_DMA_DEVICE_INFORMATION
 - wdm/_IOMMU_DMA_DEVICE_INFORMATION
 - PIOMMU_DMA_DEVICE_INFORMATION
 - wdm/PIOMMU_DMA_DEVICE_INFORMATION
 - IOMMU_DMA_DEVICE_INFORMATION
 - wdm/IOMMU_DMA_DEVICE_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _IOMMU_DMA_DEVICE_INFORMATION
---

## -description

Contains information about an IOMMU DMA device's PASID (Process Address Space Identifier) capabilities and configuration. This structure is returned by the [**IOMMU_DEVICE_QUERY_INFORMATION**](nc-wdm-iommu_device_query_information.md) function.

## -struct-fields

### -field DefaultPasidEnabled

A **BOOLEAN** value that indicates whether the device has a default PASID enabled. When TRUE, the device operates with a default PASID for DMA operations. When FALSE, the device does not have a default PASID configured.

### -field PasidTaggedDmaEnabled

A **BOOLEAN** value that indicates whether the device supports PASID-tagged DMA operations. When TRUE, the device can perform DMA operations with PASID tags, enabling multiple address spaces. When FALSE, the device does not support PASID-tagged DMA.

### -field PasidFaultsSuppressed

A **BOOLEAN** value that indicates whether PASID-related faults are suppressed for this device. When TRUE, PASID faults are suppressed and will not be reported. When FALSE, PASID faults will be reported normally.

## -remarks

This structure provides essential information about a device's PASID capabilities, which are used for advanced memory management scenarios.

## -see-also

[**IOMMU_DEVICE_QUERY_INFORMATION**](nc-wdm-iommu_device_query_information.md)

[**IOMMU_PASID_DEVICE_CREATE**](nc-wdm-iommu_pasid_device_create.md)

[**DMA_IOMMU_INTERFACE_V3**](ns-wdm-dma_iommu_interface_v3.md)
