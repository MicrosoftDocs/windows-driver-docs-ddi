---
UID: NS:ntddk._PCI_EXPRESS_SLOT_CONTROL_REGISTER
title: _PCI_EXPRESS_SLOT_CONTROL_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) slot control register of a PCIe capability structure.
old-location: pci\pci_express_slot_control_register.htm
old-project: PCI
ms.assetid: 4755f4c3-305e-41a5-afdf-eda8e8e81b74
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_SLOT_CONTROL_REGISTER, PCI_EXPRESS_SLOT_CONTROL_REGISTER, *PPCI_EXPRESS_SLOT_CONTROL_REGISTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_EXPRESS_SLOT_CONTROL_REGISTER
req.alt-loc: ntddk.h
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
req.typenames: PCI_EXPRESS_SLOT_CONTROL_REGISTER, *PPCI_EXPRESS_SLOT_CONTROL_REGISTER
---

# _PCI_EXPRESS_SLOT_CONTROL_REGISTER structure



## -description
The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) slot control register of a PCIe capability structure.



## -syntax

````
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
````


## -struct-fields

### -field AttentionButtonEnable

A single bit that indicates that the attention button for the slot is enabled to generate events.


### -field PowerFaultDetectEnable

A single bit that indicates that power fault detection for the slot is enabled to generate events.


### -field MRLSensorEnable

A single bit that indicates that the manually operated retention latch (MRL) sensor for the slot is enabled to generate events.


### -field PresenceDetectEnable

A single bit that indicates that card presence detection for the slot is enabled to generate events.


### -field CommandCompletedEnable

A single bit that indicates that notification is enabled for the slot when an issued command is completed by the hot-plug controller.


### -field HotPlugInterruptEnable

A single bit that indicates that interrupts for the slot are enabled for hot-plug events.


### -field AttentionIndicatorControl

The state of the slot's attention indicator. Possible values are:




### -field IndicatorOn

The indicator is on.


### -field IndicatorBlink

The indicator is blinking.


### -field IndicatorOff

The indicator is off.

</dd>
</dl>

### -field PowerIndicatorControl

The state of the slot's power indicator. Possible values are:




### -field IndicatorOn

The indicator is on.


### -field IndicatorBlink

The indicator is blinking.


### -field IndicatorOff

The indicator is off.

</dd>
</dl>

### -field PowerControllerControl

The state of the slot's power controller. Possible values are:




### -field PowerOn

The power is on.


### -field PowerOff

The power is off.

</dd>
</dl>

### -field ElectromechanicalLockControl

This member always contains zero.


### -field DataLinkStateChangeEnable

A single bit that indicates that notification is enabled for the slot for changes to the data link layer active bit of the link status register of the PCIe capability structure.


### -field Rsvd

Reserved.


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_SLOT_CONTROL_REGISTER structure.


## -remarks
The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SLOT_CONTROL_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SLOT_CONTROL_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

