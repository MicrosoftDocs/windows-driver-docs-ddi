---
UID: NE:wdm._IOMMU_PASID_CONFIGURATION_TYPE
tech.root: kernel
title: IOMMU_PASID_CONFIGURATION_TYPE
ms.date: 08/07/2025
targetos: Windows
description: Describes the PASID support configuration types that can be enabled for an IOMMU device. 
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
req.typenames: IOMMU_PASID_CONFIGURATION_TYPE, *PIOMMU_PASID_CONFIGURATION_TYPE
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
 - _IOMMU_PASID_CONFIGURATION_TYPE
 - PIOMMU_PASID_CONFIGURATION_TYPE
 - IOMMU_PASID_CONFIGURATION_TYPE
f1_keywords:
 - _IOMMU_PASID_CONFIGURATION_TYPE
 - wdm/_IOMMU_PASID_CONFIGURATION_TYPE
 - PIOMMU_PASID_CONFIGURATION_TYPE
 - wdm/PIOMMU_PASID_CONFIGURATION_TYPE
 - IOMMU_PASID_CONFIGURATION_TYPE
 - wdm/IOMMU_PASID_CONFIGURATION_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _IOMMU_PASID_CONFIGURATION_TYPE
---

## -description

The **IOMMU_PASID_CONFIGURATION_TYPE** enumeration describes the PASID support configuration types that can be enabled for an IOMMU device. PASID (Process Address Space Identifier) configuration types describe the support related to PASIDs that can be enabled.

## -enum-fields

### -field PasidConfigTypeDefaultPasidOnly

Indicates that the created device should be configured for untagged DMA ONLY through the default PASID, without enabling the PASID capability and other support for PASID-tagged traffic.

### -field PasidConfigTypePasidTaggedDma

Indicates that the created device should be configured for PASID-tagged DMA, which will allow for creation of PASID sub-devices (for tagged DMA). This also enables the default PASID for untagged DMA.

### -field PasidConfigTypeMax

Invalid configuration type. Used for validation purposes.

## -remarks

This enumeration is used within the [**IOMMU_DEVICE_CREATION_CONFIGURATION_PASID**](ns-wdm-iommu_device_creation_configuration_pasid.md) structure to specify the type of PASID support required for a device.

The choice between `PasidConfigTypeDefaultPasidOnly` and `PasidConfigTypePasidTaggedDma` determines whether the device will support multiple address spaces or only a single default address space.

## -see-also

[**IOMMU_DEVICE_CREATION_CONFIGURATION_PASID**](ns-wdm-iommu_device_creation_configuration_pasid.md)

[**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md)

[**IOMMU_PASID_DEVICE_CREATE**](nc-wdm-iommu_pasid_device_create.md)
