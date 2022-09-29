---
UID: NS:miniport._PCI_EXPRESS_SLOT_CONTROL_REGISTER
title: PCI_EXPRESS_SLOT_CONTROL_REGISTER (miniport.h)
description: The _PCI_EXPRESS_SLOT_CONTROL_REGISTER union (miniport.h) describes a PCI Express (PCIe) slot control register.
tech.root: PCI
ms.date: 07/19/2022
keywords: ["PCI_EXPRESS_SLOT_CONTROL_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_SLOT_CONTROL_REGISTER, PCI.pci_express_slot_control_register, PCI_EXPRESS_SLOT_CONTROL_REGISTER, PCI_EXPRESS_SLOT_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_SLOT_CONTROL_REGISTER, PPCI_EXPRESS_SLOT_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_SLOT_CONTROL_REGISTER, ntddk/PCI_EXPRESS_SLOT_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_SLOT_CONTROL_REGISTER, pci_struct_d554e74d-130d-4d6d-8801-c65ea66653cb.xml"
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
req.typenames: PCI_EXPRESS_SLOT_CONTROL_REGISTER, *PPCI_EXPRESS_SLOT_CONTROL_REGISTER
f1_keywords:
 - _PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - miniport/_PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - PPCI_EXPRESS_SLOT_CONTROL_REGISTER
 - miniport/PPCI_EXPRESS_SLOT_CONTROL_REGISTER
 - PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - miniport/PCI_EXPRESS_SLOT_CONTROL_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - PPCI_EXPRESS_SLOT_CONTROL_REGISTER
 - PCI_EXPRESS_SLOT_CONTROL_REGISTER
---

## -description

The **PCI_EXPRESS_SLOT_CONTROL_REGISTER** union describes a PCI Express (PCIe) slot control register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

The **DUMMYSTRUCTNAME** structure.

### -field DUMMYSTRUCTNAME.AttentionButtonEnable

A single bit that indicates that the attention button for the slot is enabled to generate events.

### -field DUMMYSTRUCTNAME.PowerFaultDetectEnable

A single bit that indicates that power fault detection for the slot is enabled to generate events.

### -field DUMMYSTRUCTNAME.MRLSensorEnable

A single bit that indicates that the manually operated retention latch (MRL) sensor for the slot is enabled to generate events.

### -field DUMMYSTRUCTNAME.PresenceDetectEnable

A single bit that indicates that card presence detection for the slot is enabled to generate events.

### -field DUMMYSTRUCTNAME.CommandCompletedEnable

A single bit that indicates that notification is enabled for the slot when an issued command is completed by the hot-plug controller.

### -field DUMMYSTRUCTNAME.HotPlugInterruptEnable

A single bit that indicates that interrupts for the slot are enabled for hot-plug events.

### -field DUMMYSTRUCTNAME.AttentionIndicatorControl

The state of the slot's attention indicator. Possible values are:

**IndicatorOn**  
The indicator is on.

**IndicatorBlink**  
The indicator is blinking.

**IndicatorOff**  
The indicator is off.

### -field DUMMYSTRUCTNAME.PowerIndicatorControl

The state of the slot's power indicator. Possible values are:

**IndicatorOn**  
The indicator is on.

**IndicatorBlink**  
The indicator is blinking.

**IndicatorOff**  
The indicator is off.

### -field DUMMYSTRUCTNAME.PowerControllerControl

The state of the slot's power controller. Possible values are:

**PowerOn**  
The power is on.

**PowerOff**  
The power is off.

### -field DUMMYSTRUCTNAME.ElectromechanicalLockControl

This member always contains zero.

### -field DUMMYSTRUCTNAME.DataLinkStateChangeEnable

A single bit that indicates that notification is enabled for the slot for changes to the data link layer active bit of the link status register of the PCIe capability structure.

### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_SLOT_CONTROL_REGISTER** structure.

## -remarks

The **PCI_EXPRESS_SLOT_CONTROL_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_SLOT_CONTROL_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability)
