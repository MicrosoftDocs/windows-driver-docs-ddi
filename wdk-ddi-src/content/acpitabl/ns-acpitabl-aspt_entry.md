---
UID: NS:acpitabl._ASPT_ENTRY
tech.root: acpi
title: ASPT_ENTRY (acpitabl.h)
ms.date: 03/01/2022
targetos: Windows
description: This topic describes the ASPT_ENTRY union used by the AMD Secure Processor Table (ASPT).
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
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: ASPT_ENTRY, *PASPT_ENTRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _ASPT_ENTRY
 - PASPT_ENTRY
 - ASPT_ENTRY
f1_keywords:
 - _ASPT_ENTRY
 - acpitabl/_ASPT_ENTRY
 - PASPT_ENTRY
 - acpitabl/PASPT_ENTRY
 - ASPT_ENTRY
 - acpitabl/ASPT_ENTRY
dev_langs:
 - c++
helpviewer_keywords:
 - _ASPT_ENTRY
---

## -description

This topic describes the **ASPT_ENTRY** union used by the AMD Secure Processor Table (ASPT).

## -struct-fields

### -field Header

Defines the **ASPT_ENTRY_HEADER** member **Header**.

### -field AspGlobalRegisters

Defines the **ASPT_ENTRY_ASP_GLOBAL_REGISTERS** member **AspGlobalRegisters**.

### -field SevMailboxRegisters

Defines the **ASPT_ENTRY_SEV_MAILBOX_REGISTERS** member **SevMailboxRegisters**.

### -field AcpiMailboxRegisters

Defines the **ASPT_ENTRY_ACPI_MAILBOX_REGISTERS** member **AcpiMailboxRegisters**.

## -remarks

## -see-also
