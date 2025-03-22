---
UID: NS:ntddk._WHEA_XPF_MCA_SECTION
title: _WHEA_XPF_MCA_SECTION (ntddk.h)
description: WHEA_XPF_MCA_SECTION is a machine check exception error section structure.
tech.root: whea
ms.date: 02/22/2023
keywords: ["WHEA_XPF_MCA_SECTION structure"]
ms.keywords: _WHEA_XPF_MCA_SECTION, WHEA_XPF_MCA_SECTION, *PWHEA_XPF_MCA_SECTION,
req.header: ntddk.h
req.construct-type: structure
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WHEA_XPF_MCA_SECTION, *PWHEA_XPF_MCA_SECTION
targetos: Windows
f1_keywords:
 - _WHEA_XPF_MCA_SECTION
 - ntddk/_WHEA_XPF_MCA_SECTION
 - PWHEA_XPF_MCA_SECTION
 - ntddk/PWHEA_XPF_MCA_SECTION
 - WHEA_XPF_MCA_SECTION
 - ntddk/WHEA_XPF_MCA_SECTION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_XPF_MCA_SECTION
 - PWHEA_XPF_MCA_SECTION
 - WHEA_XPF_MCA_SECTION
---

# WHEA_XPF_MCA_SECTION structure (ntddk.h)

## -description

**WHEA_XPF_MCA_SECTION** is a machine check exception error section structure.

## -struct-fields

### -field VersionNumber

Defines the **ULONG** member **VersionNumber**.

### -field CpuVendor

Defines the **WHEA_CPU_VENDOR** member **CpuVendor**.

### -field Timestamp

Defines the **LARGE_INTEGER** member **Timestamp**.

### -field ProcessorNumber

Defines the **ULONG** member **ProcessorNumber**.

### -field GlobalStatus

Defines the **MCG_STATUS** member **GlobalStatus**.

### -field InstructionPointer

Defines the **ULONGLONG** member **InstructionPointer**.

### -field BankNumber

Defines the **ULONG** member **BankNumber**.

### -field Status

Defines the **MCI_STATUS** member **Status**.

### -field Address

Defines the **ULONGLONG** member **Address**.

### -field Misc

Defines the **ULONGLONG** member **Misc**.

### -field ExtendedRegisterCount

Defines the **ULONG** member **ExtendedRegisterCount**.

### -field ApicId

Defines the **ULONG** member **ApicId**.

### -field ExtendedRegisters[WHEA_XPF_MCA_EXTREG_MAX_COUNT]

Defines the **ULONGLONG** member **ExtendedRegisters**.

### -field AMDExtendedRegisters

Defines the **WHEA_AMD_EXTENDED_REGISTERS** member **AMDExtendedRegisters**.

### -field GlobalCapability

Defines the **MCG_CAP** member **GlobalCapability**.

### -field RecoveryInfo

Defines the **XPF_RECOVERY_INFO** member **RecoveryInfo**.

### -field ExBankCount

Defines the **ULONG** member **ExBankCount**.

### -field BankNumberEx[WHEA_XPF_MCA_EXBANK_COUNT]

Defines the **ULONG** member **BankNumberEx**.

### -field StatusEx[WHEA_XPF_MCA_EXBANK_COUNT]

Defines the **MCI_STATUS** member **StatusEx**.

### -field AddressEx[WHEA_XPF_MCA_EXBANK_COUNT]

Defines the **ULONGLONG** member **AddressEx**.

### -field MiscEx[WHEA_XPF_MCA_EXBANK_COUNT]

Defines the **ULONGLONG** member **MiscEx**.

## -remarks

## -see-also
