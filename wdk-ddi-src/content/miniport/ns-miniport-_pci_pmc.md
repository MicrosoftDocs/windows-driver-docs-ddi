---
UID: NS:miniport._PCI_PMC
title: PCI_PMC (miniport.h)
description: The _PCI_PMC structure (miniport.h) describes the contents of the power management capabilities register.
tech.root: PCI
ms.date: 07/20/2022
keywords: ["PCI_PMC structure"]
ms.keywords: "*PPCI_PMC, PCI.pci_pmc, PCI_PMC, PCI_PMC structure [Buses], PPCI_PMC, PPCI_PMC structure pointer [Buses], _PCI_PMC, pci_struct_5ac33692-66a0-4c2e-89dc-e5ace757e06b.xml, wdm/PCI_PMC, wdm/PPCI_PMC"
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
req.typenames: PCI_PMC, *PPCI_PMC
f1_keywords:
 - _PCI_PMC
 - miniport/_PCI_PMC
 - PPCI_PMC
 - miniport/PPCI_PMC
 - PCI_PMC
 - miniport/PCI_PMC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_PMC
 - PPCI_PMC
 - PCI_PMC
---

## -description

The **PCI_PMC** structure is used to report the contents of the power management capabilities register.

## -struct-fields

### -field Version

Contains a 3-bit integer that indicates the version of the *PCI Power Management Interface Specification* that the device complies with. For a list of values that can be assigned to this member, see the *PCI Local Bus Specification*.

### -field PMEClock

Indicates, when 1, that the device relies on the presence of the PCI clock for operation of the PME signal. When this member is a "0", no PCI clock is required to generate the PME signal.

### -field Rsvd1

Reserved.

### -field DeviceSpecificInitialization

Indicates when 1 that the device requires a special initialization. For more information about this value, see the *PCI Local Bus Specification*.

### -field Rsvd2

Reserved.

### -field Support

The **Support** structure.

### -field Support.Rsvd2

Reserved.

### -field Support.D1

Reserved.

### -field Support.D2

Reserved.

### -field Support.PMED0

Indicates that the device can assert the PME signal from D0.

### -field Support.PMED1

Indicates that the device can assert the PME signal from D1.

### -field Support.PMED2

Indicates that the device can assert the PME signal from D2.

### -field Support.PMED3Hot

Indicates that the device can assert the PME signal from D3.

### -field Support.PMED3Cold

Indicates that the device can assert the PME signal from D3.

### -field _PM_SUPPORT

The **_PM_SUPPORT** structure.

## -remarks

The power management capabilities register, whose contents are reported in the **PCI_PMC** structure, provides information about the power management capabilities of the device.

## -see-also

[PCI_PM_CAPABILITY](../wdm/ns-wdm-_pci_pm_capability.md)