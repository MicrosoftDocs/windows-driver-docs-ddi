---
UID: NS:ntddk._PCI_EXPRESS_SLOT_CONTROL_REGISTER
title: _PCI_EXPRESS_SLOT_CONTROL_REGISTER (ntddk.h)
description: The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) slot control register of a PCIe capability structure.
old-location: pci\pci_express_slot_control_register.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_SLOT_CONTROL_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_SLOT_CONTROL_REGISTER, PCI.pci_express_slot_control_register, PCI_EXPRESS_SLOT_CONTROL_REGISTER, PCI_EXPRESS_SLOT_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_SLOT_CONTROL_REGISTER, PPCI_EXPRESS_SLOT_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_SLOT_CONTROL_REGISTER, ntddk/PCI_EXPRESS_SLOT_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_SLOT_CONTROL_REGISTER, pci_struct_d554e74d-130d-4d6d-8801-c65ea66653cb.xml"
req.header: ntddk.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: PCI_EXPRESS_SLOT_CONTROL_REGISTER, *PPCI_EXPRESS_SLOT_CONTROL_REGISTER
f1_keywords:
 - _PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - ntddk/_PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - PPCI_EXPRESS_SLOT_CONTROL_REGISTER
 - ntddk/PPCI_EXPRESS_SLOT_CONTROL_REGISTER
 - PCI_EXPRESS_SLOT_CONTROL_REGISTER
 - ntddk/PCI_EXPRESS_SLOT_CONTROL_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PCI_EXPRESS_SLOT_CONTROL_REGISTER
---

# _PCI_EXPRESS_SLOT_CONTROL_REGISTER structure (ntddk.h)


## -description

The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) slot control register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_SLOT_CONTROL_REGISTER structure.


#### - AttentionButtonEnable

A single bit that indicates that the attention button for the slot is enabled to generate events.


#### - AttentionIndicatorControl

The state of the slot's attention indicator. Possible values are:





#### IndicatorOn

The indicator is on.



#### IndicatorBlink

The indicator is blinking.



#### IndicatorOff

The indicator is off.


#### - CommandCompletedEnable

A single bit that indicates that notification is enabled for the slot when an issued command is completed by the hot-plug controller.


#### - DataLinkStateChangeEnable

A single bit that indicates that notification is enabled for the slot for changes to the data link layer active bit of the link status register of the PCIe capability structure.


#### - ElectromechanicalLockControl

This member always contains zero.


#### - HotPlugInterruptEnable

A single bit that indicates that interrupts for the slot are enabled for hot-plug events.


#### - MRLSensorEnable

A single bit that indicates that the manually operated retention latch (MRL) sensor for the slot is enabled to generate events.


#### - PowerControllerControl

The state of the slot's power controller. Possible values are:





#### PowerOn

The power is on.



#### PowerOff

The power is off.


#### - PowerFaultDetectEnable

A single bit that indicates that power fault detection for the slot is enabled to generate events.


#### - PowerIndicatorControl

The state of the slot's power indicator. Possible values are:





#### IndicatorOn

The indicator is on.



#### IndicatorBlink

The indicator is blinking.



#### IndicatorOff

The indicator is off.


#### - PresenceDetectEnable

A single bit that indicates that card presence detection for the slot is enabled to generate events.


#### - Rsvd

Reserved.

## -syntax

```cpp
typedef union _PCI_EXPRESS_SLOT_CONTROL_REGISTER {
  struct {
    USHORT AttentionButtonEnable  :1;
    USHORT PowerFaultDetectEnable  :1;
    USHORT MRLSensorEnable;
    USHORT PresenceDetectEnable  :1;
    USHORT CommandCompletedEnable  :1;
    USHORT HotPlugInterruptEnable  :1;
    USHORT AttentionIndicatorControl  :2;
    USHORT PowerIndicatorControl  :2;
    USHORT PowerControllerControl  :1;
    USHORT ElectromechanicalLockControl  :1;
    USHORT DataLinkStateChangeEnable  :1;
    USHORT Rsvd  :3;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_SLOT_CONTROL_REGISTER, *PPCI_EXPRESS_SLOT_CONTROL_REGISTER;
```

## -remarks

The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SLOT_CONTROL_REGISTER structure is contained in the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a>
