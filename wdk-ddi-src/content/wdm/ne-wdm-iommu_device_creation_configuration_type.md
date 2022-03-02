---
UID: NE:wdm._IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
tech.root: kernel
title: IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
ms.date: 03/01/2022
targetos: Windows
description: Describes the configuration types that are used upon IOMMU_DMA_DEVICE creation depending on the device type and the system.
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
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - PIOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
f1_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - wdm/_IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - PIOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - wdm/PIOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
 - wdm/IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE
---

## -description

Describes the configuration types that are used upon **IOMMU_DMA_DEVICE** creation depending on the device type and the system.

## -enum-fields

### -field IommuDeviceCreationConfigTypeNone

Default no type.

### -field IommuDeviceCreationConfigTypeAcpi

Provides ACPI device specific parameters. This is currently used for ARM64 only. See [**IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI**](ns-wdm-iommu_device_creation_configuration_acpi.md).

### -field IommuDeviceCreationConfigTypeDeviceId

Defines the **IommuDeviceCreationConfigTypeDeviceId** constant.

### -field IommuDeviceCreationConfigTypeMax

Invalid type.

## -remarks

## -see-also

[**IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI**](ns-wdm-iommu_device_creation_configuration_acpi.md)

[**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md)

[**IOMMU_DEVICE_CREATE**](nc-wdm-iommu_device_create.md)
