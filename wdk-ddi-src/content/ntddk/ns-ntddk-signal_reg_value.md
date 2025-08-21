---
UID: NS:ntddk._SIGNAL_REG_VALUE
tech.root: kernel
title: SIGNAL_REG_VALUE (ntddk.h)
ms.date: 08/20/2025
targetos: Windows
description: This topic describes the SIGNAL_REG_VALUE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: SIGNAL_REG_VALUE, *PSIGNAL_REG_VALUE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _SIGNAL_REG_VALUE
 - PSIGNAL_REG_VALUE
 - SIGNAL_REG_VALUE
f1_keywords:
 - _SIGNAL_REG_VALUE
 - ntddk/_SIGNAL_REG_VALUE
 - PSIGNAL_REG_VALUE
 - ntddk/PSIGNAL_REG_VALUE
 - SIGNAL_REG_VALUE
 - ntddk/SIGNAL_REG_VALUE
dev_langs:
 - c++
helpviewer_keywords:
 - _SIGNAL_REG_VALUE
---

## -description

The **SIGNAL_REG_VALUE** structure represents a RAS (Reliability, Availability, and Serviceability) signal register entry that contains register name, MSR address, and value information.

## -struct-fields

### -field RegName

A **UINT8** array that contains the name of the RAS register. The maximum length is defined by `WCS_RAS_REGISTER_NAME_MAX_LENGTH`.

### -field MsrAddr

A **UINT32** value that specifies the Model Specific Register (MSR) address for this RAS signal register.

### -field Value

A **UINT64** value that contains the current value stored in the RAS signal register.

## -remarks

This structure is used as part of the EFI ACPI RAS Signal Table for hardware error reporting and signaling mechanisms.

It's used as an array element within the [**EFI_ACPI_RAS_SIGNAL_TABLE**](ns-ntddk-efi_acpi_ras_signal_table.md) structure. Each entry represents a specific RAS signal register that can be monitored for hardware error conditions.

This structure is primarily used by the Windows Hardware Error Architecture (WHEA) subsystem for logging RAS table entries through ETW (Event Tracing for Windows) events. The structure allows the system to track and report on specific hardware registers that are relevant for reliability and error detection.

When multiple **SIGNAL_REG_VALUE** entries need to be logged, they may be split across multiple ETW events if the total size exceeds the maximum event size limit.

## -see-also

[**EFI_ACPI_RAS_SIGNAL_TABLE**](ns-ntddk-efi_acpi_ras_signal_table.md)
