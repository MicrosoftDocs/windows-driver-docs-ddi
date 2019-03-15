---
UID: NS:wdm._FAULT_INFORMATION_ARM64_FLAGS
title: _FAULT_INFORMATION_ARM64_FLAGS (wdm.h)
description: Defines fault information.
ms.assetid: bc0bc41d-9bc5-4d6a-98ce-1292d500c1bc
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _FAULT_INFORMATION_ARM64_FLAGS, FAULT_INFORMATION_ARM64_FLAGS, *PFAULT_INFORMATION_ARM64_FLAGS, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: FAULT_INFORMATION_ARM64_FLAGS, *PFAULT_INFORMATION_ARM64_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wdm.h
api_name: 
- _FAULT_INFORMATION_ARM64_FLAGS
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _FAULT_INFORMATION_ARM64_FLAGS structure

## -description
Defines fault information. These values are used by the [**FAULT_INFORMATION_ARM64**](ns-wdm-_fault_information_arm64.md) structure.

## -struct-fields

### -field WriteNotRead
Indicates if write permission was requested.
 
### -field InstructionNotData
Indicates if execute permission was requested.
 
### -field Privileged
Indicates if supervisor privilege was requested by the faulted request.
 
### -field FaultAddressValid
Indicates if the fault address is valid.
 
### -field Reserved
Reserved. 

## -remarks

## -see-also
