---
UID: NS:wdm._FAULT_INFORMATION
title: _FAULT_INFORMATION
author: windows-driver-content
description: Contains information to set the fault report on a device.
ms.assetid: 26ccbf2c-be6b-4c8c-8bd1-57977f7b4263
ms.date: 
ms.topic: struct
ms.keywords: _FAULT_INFORMATION, *PFAULT_INFORMATION, FAULT_INFORMATION, 
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
req.typenames: FAULT_INFORMATION, *PFAULT_INFORMATION
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	_FAULT_INFORMATION
product:
-	Windows
targetos: Windows
---

# _FAULT_INFORMATION structure

## -description
Contains information to set the fault report on a device. This structure is used by the [**IOMMU_DOMAIN_FAULT_HANDLER**](nc-wdm-iommu_domain_fault_handler.md) callback function.

## -struct-fields

### -field Type
A [**FAULT_INFORMATION_ARCH**](ne-wdm-_fault_information_arch.md)-type value that indicates the system architecture.

### -field Arm64
A [**FAULT_INFORMATION_ARM64**](ns-wdm-_fault_information_arm64.md) structure that contains fault information on an ARM64 system. 

## -remarks

## -see-also
