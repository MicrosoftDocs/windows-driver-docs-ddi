---
UID: NS:ntddk._WHEA_XPF_MC_BANK_DESCRIPTOR
title: _WHEA_XPF_MC_BANK_DESCRIPTOR (ntddk.h)
description: The WHEA_XPF_MC_BANK_DESCRIPTOR structure describes a bank of machine check registers for an x86 or x64 processor.
tech.root: whea
ms.date: 01/11/2023
keywords: ["WHEA_XPF_MC_BANK_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_XPF_MC_BANK_DESCRIPTOR, PWHEA_XPF_MC_BANK_DESCRIPTOR, PWHEA_XPF_MC_BANK_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_XPF_MC_BANK_DESCRIPTOR, WHEA_XPF_MC_BANK_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_MC_BANK_DESCRIPTOR, ntddk/PWHEA_XPF_MC_BANK_DESCRIPTOR, ntddk/WHEA_XPF_MC_BANK_DESCRIPTOR, whea.whea_xpf_mc_bank_descriptor, whearef_9f1970bd-6dbf-4104-9525-2018ab2f766e.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WHEA_XPF_MC_BANK_DESCRIPTOR, *PWHEA_XPF_MC_BANK_DESCRIPTOR
f1_keywords:
 - _WHEA_XPF_MC_BANK_DESCRIPTOR
 - ntddk/_WHEA_XPF_MC_BANK_DESCRIPTOR
 - PWHEA_XPF_MC_BANK_DESCRIPTOR
 - ntddk/PWHEA_XPF_MC_BANK_DESCRIPTOR
 - WHEA_XPF_MC_BANK_DESCRIPTOR
 - ntddk/WHEA_XPF_MC_BANK_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_XPF_MC_BANK_DESCRIPTOR
 - PWHEA_XPF_MC_BANK_DESCRIPTOR
 - WHEA_XPF_MC_BANK_DESCRIPTOR
---

## -description

The **WHEA_XPF_MC_BANK_DESCRIPTOR** structure describes a bank of machine check registers for an x86 or x64 processor.

## -struct-fields

### -field BankNumber

The processor machine check register bank number.

### -field ClearOnInitialization

A Boolean value that indicates that the status registers for the bank are to be cleared by the operating system during initialization.

### -field StatusDataFormat

The format of the data in the register bank's status register. Possible values are:

#### WHEA_XPF_MC_BANK_STATUSFORMAT_IA32MCA

IA32 machine check architecture.

#### WHEA_XPF_MC_BANK_STATUSFORMAT_Intel64MCA

Intel64 machine check architecture.

#### WHEA_XPF_MC_BANK_STATUSFORMAT_AMD64MCA

AMD64 machine check architecture.

### -field Flags

An **XPF_MC_BANK_FLAGS** union that indicates which of the members of the **WHEA_XPF_MC_BANK_DESCRIPTOR** structure can be written to by the operating system. The **XPF_MC_BANK_FLAGS** union is defined as follows:

```cpp
typedef union _XPF_MC_BANK_FLAGS {
  struct {
    UCHAR  ClearOnInitializationRW:1;
    UCHAR  ControlDataRW:1;
    UCHAR  Reserved:6;
  };
  UCHAR  AsUCHAR;
} XPF_MC_BANK_FLAGS, *PXPF_MC_BANK_FLAGS;
```

#### ClearOnInitializationRW

A single bit that indicates that the operating system can write to the **ClearOnInitialization** member of the **WHEA_XPF_MC_BANK_DESCRIPTOR** structure.

#### ControlDataRW

A single bit that indicates that the operating system can write to the **ControlData** member of the **WHEA_XPF_MC_BANK_DESCRIPTOR** structure.

#### Reserved

Reserved for system use.

#### AsUCHAR

A UCHAR representation of contents of the **XPF_MC_BANK_FLAGS** union.

### -field ControlMsr

The model-specific register address of the register bank's IA32_MCi_CTL register. For more information about the IA32_MCi_CTL register, see the [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html).

### -field StatusMsr

The model-specific register address of the register bank's IA32_MCi_STATUS register. For more information about the IA32_MCi_STATUS register, see the [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html).

### -field AddressMsr

The model-specific register address of the register bank's IA32_MCi_ADDR register. For more information about the IA32_MCi_ADDR register, see the [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html).

### -field MiscMsr

The model-specific register address of the register bank's IA32_MCi_MISC register. For more information about the IA32_MCi_MISC register, see the [Intel 64 and IA-32 Architectures Software Developer's Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html).

### -field ControlData

The value that the operating system writes to the register bank's control register during initialization.

## -remarks

An array of WHEA_XPF_MC_BANK_DESCRIPTOR structures is contained in the [**WHEA_XPF_CMC_DESCRIPTOR**](./ns-ntddk-_whea_xpf_cmc_descriptor.md) and [**WHEA_XPF_MCE_DESCRIPTOR**](./ns-ntddk-_whea_xpf_mce_descriptor.md) structures.

## -see-also

[**WHEA_XPF_CMC_DESCRIPTOR**](./ns-ntddk-_whea_xpf_cmc_descriptor.md)

[**WHEA_XPF_MCE_DESCRIPTOR**](./ns-ntddk-_whea_xpf_mce_descriptor.md)