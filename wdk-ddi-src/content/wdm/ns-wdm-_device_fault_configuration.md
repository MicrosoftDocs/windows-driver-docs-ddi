---
UID: NS:wdm._DEVICE_FAULT_CONFIGURATION
title: _DEVICE_FAULT_CONFIGURATION (wdm.h)
description: This structure is used in seting the device fault reporting state
ms.assetid: ccd97b0c-9ecc-47e3-b0c3-1c202139b06b
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _DEVICE_FAULT_CONFIGURATION, DEVICE_FAULT_CONFIGURATION, *PDEVICE_FAULT_CONFIGURATION, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DEVICE_FAULT_CONFIGURATION, *PDEVICE_FAULT_CONFIGURATION
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wdm.h
api_name: 
-	_DEVICE_FAULT_CONFIGURATION
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _DEVICE_FAULT_CONFIGURATION structure

## -description
This structure is used in seting the device fault reporting state through the [IOMMU_SET_DEVICE_FAULT_REPORTING](nc-wdm-iommu_set_device_fault_reporting.md) callback function.

## -struct-fields

### -field FaultHandler
A pointer to the driver-supplied fault handler routine, executed at PASSIVE_LEVEL. See [**IOMMU_DEVICE_FAULT_HANDLER**](nc-wdm-iommu_device_fault_handler.md).

### -field FaultContext
A pointer to the opaque driver-supplied fault context.

## -remarks

## -see-also
