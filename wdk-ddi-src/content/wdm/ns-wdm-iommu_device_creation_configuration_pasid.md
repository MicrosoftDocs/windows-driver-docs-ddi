---
UID: NS:wdm._IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
tech.root: kernel
title: IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
ms.date: 08/07/2025
targetos: Windows
description: Provides PASID-specific configuration parameters for IOMMU device creation. 
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
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_DEVICE_CREATION_CONFIGURATION_PASID, *PIOMMU_DEVICE_CREATION_CONFIGURATION_PASID
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
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - PIOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
f1_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - wdm/_IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - PIOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - wdm/PIOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
 - wdm/IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
dev_langs:
 - c++
helpviewer_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_PASID
---

## -description

The **IOMMU_DEVICE_CREATION_CONFIGURATION_PASID** structure provides PASID-specific configuration parameters for an [**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md) structure, which is used during the creation of an IOMMU_DMA_DEVICE with PASID support.

## -struct-fields

### -field ConfigType

A [**IOMMU_PASID_CONFIGURATION_TYPE**](ne-wdm-iommu_pasid_configuration_type.md) value that indicates the type of PASID support.

### -field SuppressPasidFaults

A **BOOLEAN** value that specifies whether faults related to PASID-tagged DMA traffic should be silenced. When TRUE, PASID faults are suppressed. When FALSE (the default), faults are fatal and will be reported.

## -remarks

This structure is used when creating an IOMMU device that requires PASID (Process Address Space Identifier) support. It specifies both the type of PASID configuration and fault handling behavior.

The **ConfigType** field determines whether the device will support only a default PASID or full PASID-tagged DMA capabilities. The **SuppressPasidFaults** field allows drivers to control fault reporting behavior for PASID-related operations.

## -see-also

[**IOMMU_PASID_CONFIGURATION_TYPE**](ne-wdm-iommu_pasid_configuration_type.md)

[**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md)

[**IOMMU_DEVICE_CREATE**](nc-wdm-iommu_device_create.md)

[**IOMMU_PASID_DEVICE_CREATE**](nc-wdm-iommu_pasid_device_create.md)
