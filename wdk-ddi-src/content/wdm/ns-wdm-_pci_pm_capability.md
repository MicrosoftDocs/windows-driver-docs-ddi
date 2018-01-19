---
UID: NS:wdm._PCI_PM_CAPABILITY
title: _PCI_PM_CAPABILITY
author: windows-driver-content
description: The PCI_PM_CAPABILITY structure reports the power management capabilities of the device.
old-location: pci\pci_pm_capability.htm
old-project: PCI
ms.assetid: 829d4df0-2dc2-4a1f-9606-3d5f25624252
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_PM_CAPABILITY, *PPCI_PM_CAPABILITY, PCI_PM_CAPABILITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_PM_CAPABILITY
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: *PPCI_PM_CAPABILITY, PCI_PM_CAPABILITY
req.product: Windows 10 or later.
---

# _PCI_PM_CAPABILITY structure



## -description
The PCI_PM_CAPABILITY structure reports the power management capabilities of the device.



## -syntax

````
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
````


## -struct-fields

### -field Header

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a> that identifies the capability and provides a link to the next capability description. 


### -field PMC


### -field Capabilities

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a> that specifies the power management capabilities of the device. This information was retrieved from the power management capabilities register (offset 2 in the power management register block). For more information about the contents of the power management capabilities register, see the <i>PCI Power Management Specification</i>. 


### -field AsUSHORT

Contains the same data as the <b>Capabilities </b>member. 

</dd>
</dl>

### -field PMCSR


### -field ControlStatus

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a> that reports the contents of the power management control status register. This register is used to monitor power management event signals and manage the device's power state. For more information about the contents of the power management control status register, see the <i>PCI Power Management Specification</i>. 


### -field AsUSHORT

Contains the same data as the <b>Capabilities </b>member. 

</dd>
</dl>

### -field PMCSR_BSE


### -field BridgeSupport

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a> that reports the contents of the power management control status register for PCI bridge support extensions. 


### -field AsUCHAR

Contains the same data as the <b>BridgeSupport</b> member.

</dd>
</dl>

### -field Data

Holds the contents of an optional data register that the device uses to report state-dependent operating data, such as heat dissipation or how much power the device has consumed.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_PM_CAPABILITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

