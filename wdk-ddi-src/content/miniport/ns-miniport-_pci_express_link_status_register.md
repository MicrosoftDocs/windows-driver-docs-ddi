---
UID: NS:miniport._PCI_EXPRESS_LINK_STATUS_REGISTER
title: PCI_EXPRESS_LINK_STATUS_REGISTER (miniport.h)
description: The _PCI_EXPRESS_LINK_STATUS_REGISTER union (miniport.h) describes a PCI Express (PCIe) link status register of a PCIe capability structure.
tech.root: PCI
ms.date: 07/18/2022
keywords: ["PCI_EXPRESS_LINK_STATUS_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_LINK_STATUS_REGISTER, PCI.pci_express_link_status_register, PCI_EXPRESS_LINK_STATUS_REGISTER, PCI_EXPRESS_LINK_STATUS_REGISTER union [Buses], PPCI_EXPRESS_LINK_STATUS_REGISTER, PPCI_EXPRESS_LINK_STATUS_REGISTER union pointer [Buses], _PCI_EXPRESS_LINK_STATUS_REGISTER, ntddk/PCI_EXPRESS_LINK_STATUS_REGISTER, ntddk/PPCI_EXPRESS_LINK_STATUS_REGISTER, pci_struct_41d11df3-521f-4709-a30e-be70ad36db8f.xml"
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
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
req.typenames: PCI_EXPRESS_LINK_STATUS_REGISTER, *PPCI_EXPRESS_LINK_STATUS_REGISTER
f1_keywords:
 - _PCI_EXPRESS_LINK_STATUS_REGISTER
 - miniport/_PCI_EXPRESS_LINK_STATUS_REGISTER
 - PPCI_EXPRESS_LINK_STATUS_REGISTER
 - miniport/PPCI_EXPRESS_LINK_STATUS_REGISTER
 - PCI_EXPRESS_LINK_STATUS_REGISTER
 - miniport/PCI_EXPRESS_LINK_STATUS_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_LINK_STATUS_REGISTER
 - PPCI_EXPRESS_LINK_STATUS_REGISTER
 - PCI_EXPRESS_LINK_STATUS_REGISTER
---

## -description

The **PCI_EXPRESS_LINK_STATUS_REGISTER** union describes a PCI Express (PCIe) link status register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.LinkSpeed

The negotiated link speed of the PCIe link.  Possible values are:

| Value | Description |
|--|--|
| **1** | 2.5 gigabits per second. |
| **2** | 5.0 gigabits per second. |
| All other values | Reserved. |

### -field DUMMYSTRUCTNAME.LinkWidth

The negotiated link width (number of lanes) of the PCIe link. Possible values are:

| Value | Description |
|--|--|
| **1** | x1 (1 lane) |
| **2** | x2 (2 lanes) |
| **4** | x4 (4 lanes) |
| **8** | x8 (8 lanes) |
| **12** | x12 (12 lanes) |
| **16** | x16 (16 lanes) |
| **32** | x32 (32 lanes) |
| All other values | Reserved. |

### -field DUMMYSTRUCTNAME.Undefined

Reserved. Device drivers and other system software should ignore any value read from this bit.

### -field DUMMYSTRUCTNAME.LinkTraining

A single bit that indicates that the link is in the configuration or recovery state, or that a 1 was written to the retrain link bit of the PCIe link control register and the training has not yet begun. This member is not applicable to endpoint devices and upstream ports of switches.

### -field DUMMYSTRUCTNAME.SlotClockConfig

A single bit that indicates that the component uses the same physical reference clock that the hardware platform provides on the PCIe slot connector. If this bit is clear, the component uses an independent clock irrespective of the presence of a reference clock on the PCIe slot connector.

### -field DUMMYSTRUCTNAME.DataLinkLayerActive

A single bit that indicates that the data link control and management state machine is in the data link active state.

### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_LINK_STATUS_REGISTER structure.

## -remarks

The PCI_EXPRESS_LINK_STATUS_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_LINK_STATUS_REGISTER structure is contained in the [PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md)