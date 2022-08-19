---
UID: NS:miniport._PCI_PM_CAPABILITY
title: PCI_PM_CAPABILITY (miniport.h)
description: The _PCI_PM_CAPABILITY structure (miniport.h) contains fields that describe the power management capabilities of the device.
tech.root: PCI
ms.date: 07/20/2022
keywords: ["PCI_PM_CAPABILITY structure"]
ms.keywords: "*PPCI_PM_CAPABILITY, PCI.pci_pm_capability, PCI_PM_CAPABILITY, PCI_PM_CAPABILITY structure [Buses], PPCI_PM_CAPABILITY, PPCI_PM_CAPABILITY structure pointer [Buses], _PCI_PM_CAPABILITY, pci_struct_041a9702-7b1e-43dc-8b8c-0371bc0eac26.xml, wdm/PCI_PM_CAPABILITY, wdm/PPCI_PM_CAPABILITY"
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
req.typenames: PCI_PM_CAPABILITY, *PPCI_PM_CAPABILITY
f1_keywords:
 - _PCI_PM_CAPABILITY
 - miniport/_PCI_PM_CAPABILITY
 - PPCI_PM_CAPABILITY
 - miniport/PPCI_PM_CAPABILITY
 - PCI_PM_CAPABILITY
 - miniport/PCI_PM_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_PM_CAPABILITY
 - PPCI_PM_CAPABILITY
 - PCI_PM_CAPABILITY
---

## -description

The **PCI_PM_CAPABILITY** structure reports the power management capabilities of the device.

## -struct-fields

### -field Header

Contains a structure of type [PCI_CAPABILITIES_HEADER](../wdm/ns-wdm-_pci_capabilities_header.md) that identifies the capability and provides a link to the next capability description.

### -field PMC

The power management capabilities union (offset = 2).

### -field PMC.Capabilities

Contains a structure of type [PCI_PMC](../wdm/ns-wdm-_pci_pmc.md) that specifies the power management capabilities of the device. This information was retrieved from the power management capabilities register (offset 2 in the power management register block). For more information about the contents of the power management capabilities register, see the *PCI Power Management Specification*.

### -field PMC.AsUSHORT

Contains the same data as the **Capabilities** member.

### -field PMCSR

The power management control/status union (offset = 4).

### -field PMCSR.ControlStatus

Contains a structure of type [PCI_PMCSR](../wdm/ns-wdm-_pci_pmcsr.md) that reports the contents of the power management control status register. This register is used to monitor power management event signals and manage the device's power state. For more information about the contents of the power management control status register, see the *PCI Power Management Specification*.

### -field PMCSR.AsUSHORT

Contains the same data as the **ControlStatus** member.

### -field PMCSR_BSE

The PMCSR PCI-PCI bridge support extensions union.

### -field PMCSR_BSE.BridgeSupport

Contains a structure of type [PCI_PMCSR_BSE](../wdm/ns-wdm-_pci_pmcsr_bse.md) that reports the contents of the power management control status register for PCI bridge support extensions.

### -field PMCSR_BSE.AsUCHAR

Contains the same data as the **BridgeSupport** member.

### -field Data

Holds the contents of an optional data register that the device uses to report state-dependent operating data, such as heat dissipation or how much power the device has consumed.

## -see-also

[PCI_PMCSR](../wdm/ns-wdm-_pci_pmcsr.md)

[PCI_CAPABILITIES_HEADER](../wdm/ns-wdm-_pci_capabilities_header.md)

[PCI_PMC](../wdm/ns-wdm-_pci_pmc.md)

[PCI_PMCSR_BSE](../wdm/ns-wdm-_pci_pmcsr_bse.md)