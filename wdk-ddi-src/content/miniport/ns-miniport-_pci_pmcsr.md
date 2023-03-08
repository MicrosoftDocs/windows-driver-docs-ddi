---
UID: NS:miniport._PCI_PMCSR
title: _PCI_PMCSR (miniport.h)
description: The _PCI_PMCSR structure (miniport.h) describes the contents of the device's power management control status register.
tech.root: PCI
ms.date: 03/03/2023
keywords: ["PCI_PMCSR structure"]
ms.keywords: "*PPCI_PMCSR, PCI.pci_pmcsr, PCI_PMCSR, PCI_PMCSR structure [Buses], PPCI_PMCSR, PPCI_PMCSR structure pointer [Buses], _PCI_PMCSR, pci_struct_03c3c722-9aa9-4fff-a50e-4499122d7490.xml, wdm/PCI_PMCSR, wdm/PPCI_PMCSR"
req.header: miniport.h
req.include-header: Wdm.h, Miniport.h
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: PCI_PMCSR, *PPCI_PMCSR
f1_keywords:
 - _PCI_PMCSR
 - miniport/_PCI_PMCSR
 - PPCI_PMCSR
 - miniport/PPCI_PMCSR
 - PCI_PMCSR
 - miniport/PCI_PMCSR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_PMCSR
 - PPCI_PMCSR
 - PCI_PMCSR
---

## -description

The PCI_PMCSR structure is used to report the contents of the device's power management control status register.

## -struct-fields

### -field PowerState

Indicates the power state of the device. This member can have the following values:

| Value | Meaning |
|---|---|
| 0x00 | Indicates that the device is in D0. |
| 0x01 | Indicates that the device is in D1. |
| 0x02 | Indicates that the device is in D2. |
| 0x03 | Indicates that the device is in D3. |

For more information about the power state register, see the *PCI Power Management Specification*.

### -field Rsvd1

Reserved.

### -field NoSoftReset

### -field Rsvd2

Reserved.

### -field PMEEnable

Indicates, when 1, that the device is enabled to assert the PME signal. When 0, the device is not enabled to assert the PME signal. For more information about the meaning of the PME Enable bit, see the *PCI Power Management Specification*.

### -field DataSelect

Indicates which data is to be reported through the data register. For more information about the values that this member can hold, see the *PCI Power Management Specification*.

### -field DataScale

Indicates the scaling factor used to interpret the value of the data register. For more information about the values that this member can hold, see the *PCI Power Management Specification*.

### -field PMEStatus

Contains a one-bit value (either 0 or 1) that reports the value of the PMEStatus bit in the power management register. For more information about the values that this member can hold, see the *PCI Power Management Specification*.

## -syntax

```cpp
typedef struct _PCI_PMCSR {
  USHORT PowerState  :2;
  USHORT Rsvd1  :6;
  USHORT PMEEnable  :1;
  USHORT DataSelect  :4;
  USHORT DataScale  :2;
  USHORT PMEStatus  :1;
} PCI_PMCSR, *PPCI_PMCSR;
```

## -see-also

[PCI_PM_CAPABILITY](/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pm_capability)
