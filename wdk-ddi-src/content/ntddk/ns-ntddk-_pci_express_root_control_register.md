---
UID: NS:ntddk._PCI_EXPRESS_ROOT_CONTROL_REGISTER
title: _PCI_EXPRESS_ROOT_CONTROL_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) root control register of a PCIe capability structure.
old-location: pci\pci_express_root_control_register.htm
old-project: PCI
ms.assetid: 0f2c321c-f03b-4655-bbd1-25fcc6c52cfa
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_ROOT_CONTROL_REGISTER, *PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI_EXPRESS_ROOT_CONTROL_REGISTER
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
req.alt-api: PCI_EXPRESS_ROOT_CONTROL_REGISTER
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
req.typenames: *PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI_EXPRESS_ROOT_CONTROL_REGISTER
---

# _PCI_EXPRESS_ROOT_CONTROL_REGISTER structure



## -description
The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) root control register of a PCIe capability structure.



## -syntax

````
typedef union _PCI_EXPRESS_ROOT_CONTROL_REGISTER {
  struct {
    USHORT CorrectableSerrEnable  :1;
    USHORT NonFatalSerrEnable  :1;
    USHORT FatalSerrEnable  :1;
    USHORT PMEInterruptEnable  :1;
    USHORT CRSSoftwareVisibilityEnable  :1;
    USHORT Rsvd  :11;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_ROOT_CONTROL_REGISTER, *PPCI_EXPRESS_ROOT_CONTROL_REGISTER;
````


## -struct-fields

### -field CorrectableSerrEnable

A single bit that indicates that a system error should be generated if a correctable error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


### -field NonFatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


### -field FatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


### -field PMEInterruptEnable

A single bit that indicates that interrupts are enabled for power management events.


### -field CRSSoftwareVisibilityEnable

A single bit that indicates that the root port is enabled to return configuration request retry status (CRS) completion status to software.


### -field Rsvd

Reserved.


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_ROOT_CONTROL_REGISTER structure.


## -remarks
The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_CONTROL_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ROOT_CONTROL_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

