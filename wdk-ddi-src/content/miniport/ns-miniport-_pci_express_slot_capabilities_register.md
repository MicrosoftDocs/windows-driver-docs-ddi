---
UID: NS:miniport._PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
title: PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER (miniport.h)
description: The _PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER union (miniport.h) describes a PCI Express (PCIe) slot capabilities register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, PCI.pci_express_slot_capabilities_register, PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER union [Buses], PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER union pointer [Buses], _PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, ntddk/PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, ntddk/PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, pci_struct_095f0907-dfff-491b-8734-28b42794c46b.xml"
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
req.typenames: PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER, *PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
f1_keywords:
 - _PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - miniport/_PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - miniport/PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - miniport/PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - PPCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
 - PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER
---

## -description

The **PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER** union describes a PCI Express (PCIe) slot capabilities register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.AttentionButtonPresent

A single bit that indicates that an attention button exists for the slot.

### -field DUMMYSTRUCTNAME.PowerControllerPresent

A single bit that indicates that a software programmable power controller exists for the slot or for the adapter that is plugged into the slot.

### -field DUMMYSTRUCTNAME.MRLSensorPresent

A single bit that indicates that a manually operated retention latch (MRL) sensor exists for the slot.

### -field DUMMYSTRUCTNAME.AttentionIndicatorPresent

A single bit that indicates that an attention indicator exists for the slot.

### -field DUMMYSTRUCTNAME.PowerIndicatorPresent

A single bit that indicates that a power indicator exists for the slot.

### -field DUMMYSTRUCTNAME.HotPlugSurprise

A single bit that indicates that an adapter that is present in the slot can be removed from the system without any prior notification.

### -field DUMMYSTRUCTNAME.HotPlugCapable

A single bit that indicates that the slot is capable of supporting hot-plug operations.

### -field DUMMYSTRUCTNAME.SlotPowerLimit

The maximum amount of power that can be supplied by the slot. This value is used in combination with the value of the **SlotPowerLimitScale** member to compute the power in watts.

### -field DUMMYSTRUCTNAME.SlotPowerLimitScale

The scale used for the value contained in the **SlotPowerLimit** member to compute the maximum power, in watts, that can be supplied by the slot. Possible values are:

**0**  
Multiply the value in the **SlotPowerLimit** member by 1.0.

**1**  
Multiply the value in the **SlotPowerLimit** member by 0.1.

**2**  
Multiply the value in the **SlotPowerLimit** member by 0.01.

**3**  
Multiply the value in the **SlotPowerLimit** member by 0.001.

### -field DUMMYSTRUCTNAME.ElectromechanicalLockPresent

A single bit that indicates that an electromechanical interlock exists for the slot.

### -field DUMMYSTRUCTNAME.NoCommandCompletedSupport

A single bit that indicates that the slot does not generate software notification when an issued command is completed by the hot-plug controller.

### -field DUMMYSTRUCTNAME.PhysicalSlotNumber

The physical slot number in the system chassis that is attached to this port. This value is zero for ports that are connected to devices that are either integrated on the system board or integrated within the same physical component as the switch device or root port.

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](../ntddk/ns-ntddk-_pci_express_capability.md)