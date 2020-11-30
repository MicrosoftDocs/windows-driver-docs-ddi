---
UID: NS:wdm._FAULT_INFORMATION_ARM64
title: _FAULT_INFORMATION_ARM64 (wdm.h)
description: Contains fault information for an ARM64 system.
ms.assetid: 13ff621d-7cda-4440-91bc-9184a3b44bf2
ms.date: 10/19/2018
tech.root: devtest
keywords: ["FAULT_INFORMATION_ARM64 structure"]
ms.keywords: _FAULT_INFORMATION_ARM64, FAULT_INFORMATION_ARM64, *PFAULT_INFORMATION_ARM64,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: FAULT_INFORMATION_ARM64, *PFAULT_INFORMATION_ARM64
targetos: Windows
f1_keywords:
 - _FAULT_INFORMATION_ARM64
 - wdm/_FAULT_INFORMATION_ARM64
 - PFAULT_INFORMATION_ARM64
 - wdm/PFAULT_INFORMATION_ARM64
 - FAULT_INFORMATION_ARM64
 - wdm/FAULT_INFORMATION_ARM64
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _FAULT_INFORMATION_ARM64
---

# _FAULT_INFORMATION_ARM64 structure


## -description

Describes fault information for an ARM64 system.

## -struct-fields

### -field DomainHandle

The handle to the DMA domain that the caller obtained from a previous call to [**PGET_DMA_DOMAIN**](nc-wdm-pget_dma_domain.md).

### -field FaultAddress

### -field PhysicalDeviceObject

 A pointer the physical device object (PDO) in the device stack of the device.

### -field InputMappingId

The input mapping base for the device's desired stream.

### -field Flags

A bitwise of [**FAULT_INFORMATION_ARM64_FLAGS**](ns-wdm-_fault_information_arm64_flags.md) flags.

### -field Type

A bitwise of [**FAULT_INFORMATION_ARM64_TYPE**](ne-wdm-_fault_information_arm64_type.md) flags.

## -remarks

## -see-also

