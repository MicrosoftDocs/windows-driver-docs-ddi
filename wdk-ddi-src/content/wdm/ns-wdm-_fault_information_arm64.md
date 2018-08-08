---
UID: NS:wdm._FAULT_INFORMATION_ARM64
title: _FAULT_INFORMATION_ARM64
author: windows-driver-content
description: Contains fault information for an ARM64 system. 
ms.assetid: 13ff621d-7cda-4440-91bc-9184a3b44bf2
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	_FAULT_INFORMATION_ARM64
product: Windows
targetos: Windows
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