---
UID: NS:miniport._PCI_EXPRESS_SLOT_STATUS_REGISTER
title: PCI_EXPRESS_SLOT_STATUS_REGISTER (miniport.h)
description: The _PCI_EXPRESS_SLOT_STATUS_REGISTER union (miniport.h) describes a PCI Express (PCIe) slot status register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SLOT_STATUS_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_SLOT_STATUS_REGISTER, PCI.pci_express_slot_status_register, PCI_EXPRESS_SLOT_STATUS_REGISTER, PCI_EXPRESS_SLOT_STATUS_REGISTER union [Buses], PPCI_EXPRESS_SLOT_STATUS_REGISTER, PPCI_EXPRESS_SLOT_STATUS_REGISTER union pointer [Buses], _PCI_EXPRESS_SLOT_STATUS_REGISTER, ntddk/PCI_EXPRESS_SLOT_STATUS_REGISTER, ntddk/PPCI_EXPRESS_SLOT_STATUS_REGISTER, pci_struct_2b218675-a1f4-4aec-a115-3046fac70492.xml"
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
req.typenames: PCI_EXPRESS_SLOT_STATUS_REGISTER, *PPCI_EXPRESS_SLOT_STATUS_REGISTER
f1_keywords:
 - _PCI_EXPRESS_SLOT_STATUS_REGISTER
 - miniport/_PCI_EXPRESS_SLOT_STATUS_REGISTER
 - PPCI_EXPRESS_SLOT_STATUS_REGISTER
 - miniport/PPCI_EXPRESS_SLOT_STATUS_REGISTER
 - PCI_EXPRESS_SLOT_STATUS_REGISTER
 - miniport/PCI_EXPRESS_SLOT_STATUS_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_SLOT_STATUS_REGISTER
 - PPCI_EXPRESS_SLOT_STATUS_REGISTER
 - PCI_EXPRESS_SLOT_STATUS_REGISTER
---

## -description

The **PCI_EXPRESS_SLOT_STATUS_REGISTER** union describes a PCI Express (PCIe) slot status register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.AttentionButtonPressed

A single bit that indicates that the attention button for the slot is being pressed.

### -field DUMMYSTRUCTNAME.PowerFaultDetected

A single bit that indicates that a power fault at the slot has been detected.

### -field DUMMYSTRUCTNAME.MRLSensorChanged

A single bit that indicates that the state of the slot's manually operated retention latch (MRL) sensor has changed.

### -field DUMMYSTRUCTNAME.PresenceDetectChanged

A single bit that indicates that the card presence detection state for the slot has changed.

### -field DUMMYSTRUCTNAME.CommandCompleted

A single bit that indicates that a command has been completed by the slot's hot-plug controller.

### -field DUMMYSTRUCTNAME.MRLSensorState

The slot's manually operated retention latch (MRL) sensor state. Possible values are:

**MRLClosed**  
The MRL is closed.

**MRLOpen**  
The MRL is open.

### -field DUMMYSTRUCTNAME.PresenceDetectState

The slot's card presence detection state. Possible values are:

**SlotEmpty**  
The slot is empty.

**CardPresent**  
A card is present in the slot.

### -field DUMMYSTRUCTNAME.ElectromechanicalLockEngaged

A single bit that indicates if the slot's electromechanical interlock is engaged.

### -field DUMMYSTRUCTNAME.DataLinkStateChanged

A single bit that indicates that the data link layer active bit of the PCIe link status register of the PCIe capability structure has changed.

### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_SLOT_STATUS_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_SLOT_STATUS_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SLOT_STATUS_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability)
