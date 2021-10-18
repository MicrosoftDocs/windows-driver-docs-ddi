---
UID: NS:wdm._DEVICE_BUS_SPECIFIC_RESET_TYPE
tech.root: kernel
title: DEVICE_BUS_SPECIFIC_RESET_TYPE
ms.date: 06/13/2021
targetos: Windows
description: Defines the DEVICE_BUS_SPECIFIC_RESET_TYPE structure.
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

## -description

Defines the **DEVICE_BUS_SPECIFIC_RESET_TYPE** structure.

## -struct-fields

### -field Pci

### -field Pci.FunctionLevelDeviceReset

### -field Pci.PlatformLevelDeviceReset

### -field Pci.SecondaryBusReset

### -field Pci.Reserved

### -field Acpi

### -field Acpi.FunctionLevelDeviceReset

### -field Acpi.PlatformLevelDeviceReset

### -field Acpi.Reserved

### -field AsULONGLONG

## -remarks

## -see-also
