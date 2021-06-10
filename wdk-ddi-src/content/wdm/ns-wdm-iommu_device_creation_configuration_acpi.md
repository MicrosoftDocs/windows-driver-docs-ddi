---
UID: NS:wdm._IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
tech.root: kernel
title: IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
ms.date: 06/04/2021
targetos: Windows
description: IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI provides the ACPI-specific configuration parameters of a IOMMU_DEVICE_CREATION_CONFIGURATION structure, which is provided for creation of an ACPI-type IOMMU_DMA_DEVICE.
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
req.typenames: IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI, *PIOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - PIOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
f1_keywords:
 - _IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - wdm/_IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - PIOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - wdm/PIOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
 - wdm/IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI
dev_langs:
 - c++
---

## -description

**IOMMU_DEVICE_CREATION_CONFIGURATION_ACPI** provides the ACPI-specific configuration parameters of a [**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md) structure, which is provided for creation of an ACPI-type **IOMMU_DMA_DEVICE**.

## -struct-fields

### -field InputMappingBase

Provides the input mapping base for the device's desired stream.

### -field MappingsCount

Provides the count of mappings beginning at the base.

## -remarks

This is required for ACPI devices on ARM64 systems.

## -see-also

[**IOMMU_DEVICE_CREATION_CONFIGURATION_TYPE**](ne-wdm-iommu_device_creation_configuration_type.md)

[**IOMMU_DEVICE_CREATION_CONFIGURATION**](ns-wdm-iommu_device_creation_configuration.md)

[**IOMMU_DEVICE_CREATE**](nc-wdm-iommu_device_create.md)
