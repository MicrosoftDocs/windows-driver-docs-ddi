---
UID: NS:miniport._PCI_CAPABILITIES_HEADER
title: _PCI_CAPABILITIES_HEADER (miniport.h)
description: The _PCI_CAPABILITIES_HEADER structure (miniport.h) defines a header that is present in every PCI capability structure.
tech.root: PCI
ms.date: 03/03/2023
keywords: ["PCI_CAPABILITIES_HEADER structure"]
ms.keywords: "*PPCI_CAPABILITIES_HEADER, PCI.pci_capabilities_header, PCI_CAPABILITIES_HEADER, PCI_CAPABILITIES_HEADER structure [Buses], PPCI_CAPABILITIES_HEADER, PPCI_CAPABILITIES_HEADER structure pointer [Buses], _PCI_CAPABILITIES_HEADER, pci_struct_4e7e5552-8a1b-4081-9197-df863319b01d.xml, wdm/PCI_CAPABILITIES_HEADER, wdm/PPCI_CAPABILITIES_HEADER"
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
req.typenames: PCI_CAPABILITIES_HEADER, *PPCI_CAPABILITIES_HEADER
f1_keywords:
 - _PCI_CAPABILITIES_HEADER
 - miniport/_PCI_CAPABILITIES_HEADER
 - PPCI_CAPABILITIES_HEADER
 - miniport/PPCI_CAPABILITIES_HEADER
 - PCI_CAPABILITIES_HEADER
 - miniport/PCI_CAPABILITIES_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_CAPABILITIES_HEADER
 - PPCI_CAPABILITIES_HEADER
 - PCI_CAPABILITIES_HEADER
---

## -description

The **PCI_CAPABILITIES_HEADER** structure defines a header that is present in every PCI capability structure.

## -struct-fields

### -field CapabilityID

Contains an 8-bit integer that indicates the capability ID. The capability ID identifies the type of capability structure that follows this header. The **CapabilityID** member must have one of the following values:

| Capability ID | Meaning |
|---|---|
| PCI_CAPABILITY_ID_POWER_MANAGEMENT | Indicates that the capability structure that follows the header defines a PCI power management interface. For more information about this kind of capability, see the *PCI Power Management Interface Specification*. |
| PCI_CAPABILITY_ID_AGP | Indicates that the capability structure that follows the header defines the Accelerated Graphics Port (AGP) supported by the device. For more information about this kind of capability, see the *Accelerated Graphics Port Interface Specification.* |
| PCI_CAPABILITY_ID_VPD | Indicates that the capability structure that follows the header defines Vital Product Data (VPD) features of the device. |
| PCI_CAPABILITY_ID_SLOT_ID | Indicates that the capability structure that follows the header defines external expansion capabilities of a bridge device. For more information about this kind of capability, see the *PCI to PCI Bridge Architecture Specification*. |
| PCI_CAPABILITY_ID_MSI | Indicates that the capability structure that follows the header defines a *PCI device* that can do message signaled interrupt (MSI) delivery. For more information about the MSI capability, see the *PCI Local Bus Specification*. |
| PCI_CAPABILITY_ID_CPCI_HOTSWAP | Indicates that the capability structure that follows the header defines a standard interface to control and sense status. Devices that supports hot swap insertion and extraction in a CompactPCI system require this kind of interface. For more information about control and sense status in CompactPCI systems, see the *CompactPCI Hot Swap Specification*. |
| PCI_CAPABILITY_ID_PCIX | Indicates that the capability structure that follows the header defines the devices PCI-X features. For more information about PCI-X, see the *PCI-X Addendum to the PCI Local Bus Specification*. |
| PCI_CAPABILITY_ID_HYPERTRANSPORT | Indicates that the capability structure that follows the header defines control and status for devices that implement hyper transport (HT) technology links. For more information about HT technology, refer to the *HyperTransport I/O Link Specification*. |
| PCI_CAPABILITY_ID_VENDOR_SPECIFIC | Indicates that the capability structure that follows the header defines vendor specific information. For more information about how to use the capability mechanism to communicate vendor-specific information, see the *PCI Local Bus Specification*. |
| PCI_CAPABILITY_ID_DEBUG_PORT | Indicates that the capability structure that follows the header describes a debug port |
| PCI_CAPABILITY_ID_CPCI_RES_CTRL | Indicates that the capability structure that follows the header describes CompactPCI central resource control. For more information about this kind of control see the *PICMG 2.13 Specification*. |
| PCI_CAPABILITY_ID_SHPC | Indicates that the capability structure that follows the header defines the features of a device that conforms to the standard hot-plug controller model. |
| PCI_CAPABILITY_ID_P2P_SSID | Indicates that the capability structure that follows the header defines the subsystem ID capability. |
| PCI_CAPABILITY_ID_AGP_TARGET | Indicates that the capability structure that follows the header defines the Accelerated Graphics Port (AGP) 8x capability. |
| PCI_CAPABILITY_ID_SECURE | Indicates that the capability structure that follows the header describes a secure device |
| PCI_CAPABILITY_ID_PCI_EXPRESS | Indicates that the capability structure that follows the header defines a device that supports PCI express. |
| PCI_CAPABILITY_ID_MSIX | Indicates that the capability structure that follows the header defines an optional extension to the basic MSI functionality. |

### -field Next

Contains an offset into the PCI configuration space that indicates the location of the next item in the capability list. If there are no additional items in the list, this member will contain zero.

## -syntax

```cpp
typedef struct _PCI_CAPABILITIES_HEADER {
  UCHAR CapabilityID;
  UCHAR Next;
} PCI_CAPABILITIES_HEADER, *PPCI_CAPABILITIES_HEADER;
```

## -remarks

All PCI Capability structures have the header described by PCI_CAPABILITIES_HEADER.

## -see-also

[PCI_PMCSR](../wdm/ns-wdm-_pci_pmcsr.md)

[PCI_PMC](../wdm/ns-wdm-_pci_pmc.md)

[PCI_PMCSR_BSE](../wdm/ns-wdm-_pci_pmcsr_bse.md)