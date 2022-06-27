---
UID: NS:wdm._IOMMU_DEVICE_CREATION_CONFIGURATION
tech.root: kernel
title: IOMMU_DEVICE_CREATION_CONFIGURATION (wdm.h)
ms.date: 03/02/2022
targetos: Windows
description: IOMMU_DEVICE_CREATION_CONFIGURATION describes a configuration or list of configurations to be used as part of creation and initialization of an IOMMU_DMA_DEVICE.
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
req.target-type: Windows
req.typenames: IOMMU_DEVICE_CREATION_CONFIGURATION, *PIOMMU_DEVICE_CREATION_CONFIGURATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION
 - PIOMMU_DEVICE_CREATION_CONFIGURATION
 - IOMMU_DEVICE_CREATION_CONFIGURATION
f1_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION
 - wdm/_IOMMU_DEVICE_CREATION_CONFIGURATION
 - PIOMMU_DEVICE_CREATION_CONFIGURATION
 - wdm/PIOMMU_DEVICE_CREATION_CONFIGURATION
 - IOMMU_DEVICE_CREATION_CONFIGURATION
 - wdm/IOMMU_DEVICE_CREATION_CONFIGURATION
dev_langs:
 - c++
helpviewer_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION
---

## -description

**IOMMU_DEVICE_CREATION_CONFIGURATION** describes a configuration or list of configurations to be used as part of creation and initialization of an **IOMMU_DMA_DEVICE**.

## -struct-fields

### -field NextConfiguration

Optional list to provide additional configurations.

### -field ConfigType

An enum describing which configuration is represented. See [**IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE**](ne-wdm-iommu_device_creation_configuration_type.md).

### -field Acpi

If `(ConfigType == IommuDeviceCreationConfigTypeAcpi)`, provides the input parameters necessary for device creation. See [**IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI**](ns-wdm-iommu_device_creation_configuration_acpi.md)

### -field DeviceId

Defines the **PVOID** member **DeviceId**.

## -remarks

If the device is an ACPI device on an ARM64 system, then an **IOMMU_DEVICE_CREATION_CONFIGURATION** structure must be provided during device creation, `ConfigType = IommuDeviceCreationConfigTypeAcpi`, and ACPI-specific parameters must be provided through [**IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI**](ns-wdm-iommu_device_creation_configuration_acpi.md) in the `Acpi` field.

## -see-also

[**IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE**](ne-wdm-iommu_device_creation_configuration_type.md)

[**IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI**](ns-wdm-iommu_device_creation_configuration_acpi.md)

[**IOMMU_DEVICE_CREATE**](nc-wdm-iommu_device_create.md)
