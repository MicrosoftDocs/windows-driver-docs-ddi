---
UID: NS:wdm._DEVICE_BUS_SPECIFIC_RESET_TYPE
tech.root: kernel
title: DEVICE_BUS_SPECIFIC_RESET_TYPE
ms.date: 06/13/2021
targetos: Windows
description: Defines the DEVICE_BUS_SPECIFIC_RESET_TYPE union.
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
req.typenames: DEVICE_BUS_SPECIFIC_RESET_TYPE, *PDEVICE_BUS_SPECIFIC_RESET_TYPE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DEVICE_BUS_SPECIFIC_RESET_TYPE
 - PDEVICE_BUS_SPECIFIC_RESET_TYPE
 - DEVICE_BUS_SPECIFIC_RESET_TYPE
f1_keywords:
 - _DEVICE_BUS_SPECIFIC_RESET_TYPE
 - wdm/_DEVICE_BUS_SPECIFIC_RESET_TYPE
 - PDEVICE_BUS_SPECIFIC_RESET_TYPE
 - wdm/PDEVICE_BUS_SPECIFIC_RESET_TYPE
 - DEVICE_BUS_SPECIFIC_RESET_TYPE
 - wdm/DEVICE_BUS_SPECIFIC_RESET_TYPE
dev_langs:
 - c++
---

# DEVICE_BUS_SPECIFIC_RESET_TYPE structure (wdm.h)

## -description

Defines the **DEVICE_BUS_SPECIFIC_RESET_TYPE** union.

## -struct-fields

### -field Pci

Defines the **Pci** structure.

### -field Pci.FunctionLevelDeviceReset

Defines the **ULONGLONG** member **FunctionLevelDeviceReset**.

### -field Pci.PlatformLevelDeviceReset

Defines the **ULONGLONG** member **PlatformLevelDeviceReset**.

### -field Pci.SecondaryBusReset

Defines the **ULONGLONG** member **SecondaryBusReset**.

### -field Pci.PowerControllerReset

Defines the **ULONGLONG** member **PowerControllerReset**.

### -field Pci.Reserved

Reserved for future use.

### -field Acpi

Defines the **Acpi** structure.

### -field Acpi.FunctionLevelDeviceReset

Defines the **ULONGLONG** member **FunctionLevelDeviceReset**.

### -field Acpi.PlatformLevelDeviceReset

Defines the **ULONGLONG** member **PlatformLevelDeviceReset**.

### -field Acpi.Reserved

Reserved for future use.

### -field AsULONGLONG

Defines the **ULONGLONG** member **AsULONGLONG**.

## -remarks

## -see-also
