---
UID: NS:miniport._PCI_PM_CAPABILITY
title: _PCI_PM_CAPABILITY (miniport.h)
description: The PCI_PM_CAPABILITY structure reports the power management capabilities of the device.
old-location: pci\pci_pm_capability.htm
tech.root: PCI
ms.assetid: 829d4df0-2dc2-4a1f-9606-3d5f25624252
ms.date: 02/24/2018
keywords: ["_PCI_PM_CAPABILITY structure"]
ms.keywords: "*PPCI_PM_CAPABILITY, PCI.pci_pm_capability, PCI_PM_CAPABILITY, PCI_PM_CAPABILITY structure [Buses], PPCI_PM_CAPABILITY, PPCI_PM_CAPABILITY structure pointer [Buses], _PCI_PM_CAPABILITY, pci_struct_041a9702-7b1e-43dc-8b8c-0371bc0eac26.xml, wdm/PCI_PM_CAPABILITY, wdm/PPCI_PM_CAPABILITY"
f1_keywords:
 - "miniport/PCI_PM_CAPABILITY"
 - "PCI_PM_CAPABILITY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCI_PM_CAPABILITY
targetos: Windows
req.typenames: PCI_PM_CAPABILITY, *PPCI_PM_CAPABILITY
---

# _PCI_PM_CAPABILITY structure


## -description


The PCI_PM_CAPABILITY structure reports the power management capabilities of the device.


## -syntax


```cpp
typedef struct _PCI_PM_CAPABILITY {
  PCI_CAPABILITIES_HEADER Header;
  union {
    PCI_PMC Capabilities;
    USHORT  AsUSHORT;
  } PMC;
  union {
    PCI_PMCSR ControlStatus;
    USHORT    AsUSHORT;
  } PMCSR;
  union {
    PCI_PMCSR_BSE BridgeSupport;
    UCHAR         AsUCHAR;
  } PMCSR_BSE;
  UCHAR                   Data;
} PCI_PM_CAPABILITY, *PPCI_PM_CAPABILITY;
```


## -struct-fields




### -field Header

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_capabilities_header">PCI_CAPABILITIES_HEADER</a> that identifies the capability and provides a link to the next capability description.


### -field PMC



#### Capabilities

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pmc">PCI_PMC</a> that specifies the power management capabilities of the device. This information was retrieved from the power management capabilities register (offset 2 in the power management register block). For more information about the contents of the power management capabilities register, see the <i>PCI Power Management Specification</i>.



#### AsUSHORT

Contains the same data as the <b>Capabilities </b>member.


### -field PMCSR



#### ControlStatus

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pmcsr">PCI_PMCSR</a> that reports the contents of the power management control status register. This register is used to monitor power management event signals and manage the device's power state. For more information about the contents of the power management control status register, see the <i>PCI Power Management Specification</i>.



#### AsUSHORT

Contains the same data as the <b>Capabilities </b>member.


### -field PMCSR_BSE



#### BridgeSupport

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pmcsr_bse">PCI_PMCSR_BSE</a> that reports the contents of the power management control status register for PCI bridge support extensions.



#### AsUCHAR

Contains the same data as the <b>BridgeSupport</b> member.


### -field Data

Holds the contents of an optional data register that the device uses to report state-dependent operating data, such as heat dissipation or how much power the device has consumed.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pmcsr">PCI_PMCSR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_capabilities_header">PCI_CAPABILITIES_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pmc">PCI_PMC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_pmcsr_bse">PCI_PMCSR_BSE</a>



 

 


