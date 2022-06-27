---
UID: NS:acpitabl._ASPT_ENTRY_SEV_MAILBOX_REGISTERS
tech.root: acpi
title: ASPT_ENTRY_SEV_MAILBOX_REGISTERS (acpitabl.h)
ms.date: 03/01/2022
targetos: Windows
description: This topic describes the ASPT_ENTRY_SEV_MAILBOX_REGISTERS structure used by the AMD Secure Processor Table (ASPT).
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
req.typenames: ASPT_ENTRY_SEV_MAILBOX_REGISTERS, *PASPT_ENTRY_SEV_MAILBOX_REGISTERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _ASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - PASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - ASPT_ENTRY_SEV_MAILBOX_REGISTERS
f1_keywords:
 - _ASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - acpitabl/_ASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - PASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - acpitabl/PASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - ASPT_ENTRY_SEV_MAILBOX_REGISTERS
 - acpitabl/ASPT_ENTRY_SEV_MAILBOX_REGISTERS
dev_langs:
 - c++
helpviewer_keywords:
 - _ASPT_ENTRY_SEV_MAILBOX_REGISTERS
---

## -description

This topic describes the **ASPT_ENTRY_SEV_MAILBOX_REGISTERS** structure used by the AMD Secure Processor Table (ASPT).

## -struct-fields

### -field Header

Defines the **ASPT_ENTRY_HEADER** member **Header**.

### -field MailboxInterruptId

Defines the **UINT8** member **MailboxInterruptId**.

### -field Reserved

Reserved for future use.

### -field CmdRespRegisterAddress

Defines the **UINT64** member **CmdRespRegisterAddress**.

### -field CmdBufAddrLoRegisterAddress

Defines the **UINT64** member **CmdBufAddrLoRegisterAddress**.

### -field CmdBufAddrHiRegisterAddress

Defines the **UINT64** member **CmdBufAddrHiRegisterAddress**.

## -remarks

## -see-also
