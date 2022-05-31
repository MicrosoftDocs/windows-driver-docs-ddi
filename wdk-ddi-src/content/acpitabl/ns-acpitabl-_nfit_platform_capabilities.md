---
UID: NS:acpitabl._NFIT_PLATFORM_CAPABILITIES
tech.root: acpi
title: NFIT_PLATFORM_CAPABILITIES
ms.date: 02/28/2022
targetos: Windows
description: Describes the NVDIMM Firmware Interface Table (NFIT) platform capabilities structure. Originally defined in ACPI 6.2 Errata A.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NFIT_PLATFORM_CAPABILITIES, *PNFIT_PLATFORM_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _NFIT_PLATFORM_CAPABILITIES
 - PNFIT_PLATFORM_CAPABILITIES
 - NFIT_PLATFORM_CAPABILITIES
f1_keywords:
 - _NFIT_PLATFORM_CAPABILITIES
 - acpitabl/_NFIT_PLATFORM_CAPABILITIES
 - PNFIT_PLATFORM_CAPABILITIES
 - acpitabl/PNFIT_PLATFORM_CAPABILITIES
 - NFIT_PLATFORM_CAPABILITIES
 - acpitabl/NFIT_PLATFORM_CAPABILITIES
dev_langs:
 - c++
helpviewer_keywords:
 - _NFIT_PLATFORM_CAPABILITIES
---

## -description

Describes the NVDIMM Firmware Interface Table (NFIT) platform capabilities structure. Originally defined in ACPI 6.2 Errata A.

## -struct-fields

### -field Header

Defines a **NFIT_STRUCT_HEADER** member **Header**.

### -field HighestValidCapability

Defines a **UCHAR** member **HighestValidCapability**.

### -field Reserved

Reserved for future use.

### -field Capabilities

Defines a union member **Capabilities**.

### -field Capabilities.AsUlong

Defines a **ULONG** member **AsUlong**.

### -field Capabilities.u

Defines a structure member **u**.

### -field Capabilities.u.CpuCacheFlushOnPowerLoss

Defines a **ULONG** member **CpuCacheFlushOnPowerLoss**.

### -field Capabilities.u.MemCtrlrFlushOnPowerLoss

Defines a **ULONG** member **MemCtrlrFlushOnPowerLoss**.

### -field Capabilities.u.PmemHardwareMirroring

Defines a **ULONG** member **PmemHardwareMirroring**.

### -field Reserved1

Reserved for future use.

## -remarks

## -see-also
