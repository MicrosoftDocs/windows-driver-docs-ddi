---
UID: NS:wdm._PCI_PM_CAPABILITY
title: "_PCI_PM_CAPABILITY"
author: windows-driver-content
description: The PCI_PM_CAPABILITY structure reports the power management capabilities of the device.
old-location: pci\pci_pm_capability.htm
old-project: PCI
ms.assetid: 829d4df0-2dc2-4a1f-9606-3d5f25624252
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPCI_PM_CAPABILITY, ,, A, B, C, I, L, M, P, PCI.pci_pm_capability, PCI_PM_CAPABILITY, PCI_PM_CAPABILITY structure [Buses], PPCI_PM_CAPABILITY, PPCI_PM_CAPABILITY structure pointer [Buses], T, Y, _, _PCI_PM_CAPABILITY, pci_struct_041a9702-7b1e-43dc-8b8c-0371bc0eac26.xml, wdm/PCI_PM_CAPABILITY, wdm/PPCI_PM_CAPABILITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCI_PM_CAPABILITY
product: Windows
targetos: Windows
req.typenames: PCI_PM_CAPABILITY, *PPCI_PM_CAPABILITY
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



#### Capabilities

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a> that specifies the power management capabilities of the device. This information was retrieved from the power management capabilities register (offset 2 in the power management register block). For more information about the contents of the power management capabilities register, see the <i>PCI Power Management Specification</i>. 



#### AsUSHORT

Contains the same data as the <b>Capabilities </b>member. 


### -field PMCSR



#### ControlStatus

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a> that reports the contents of the power management control status register. This register is used to monitor power management event signals and manage the device's power state. For more information about the contents of the power management control status register, see the <i>PCI Power Management Specification</i>. 



#### AsUSHORT

Contains the same data as the <b>Capabilities </b>member. 


### -field PMCSR_BSE



#### BridgeSupport

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a> that reports the contents of the power management control status register for PCI bridge support extensions. 



#### AsUCHAR

Contains the same data as the <b>BridgeSupport</b> member.


### -field Data

Holds the contents of an optional data register that the device uses to report state-dependent operating data, such as heat dissipation or how much power the device has consumed.


##### - PMC.Capabilities

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a> that specifies the power management capabilities of the device. This information was retrieved from the power management capabilities register (offset 2 in the power management register block). For more information about the contents of the power management capabilities register, see the <i>PCI Power Management Specification</i>. 


##### - PMC.AsUSHORT

Contains the same data as the <b>Capabilities </b>member. 


##### - PMCSR.ControlStatus

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a> that reports the contents of the power management control status register. This register is used to monitor power management event signals and manage the device's power state. For more information about the contents of the power management control status register, see the <i>PCI Power Management Specification</i>. 


##### - PMCSR.AsUSHORT

Contains the same data as the <b>Capabilities </b>member. 


##### - PMCSR_BSE.BridgeSupport

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a> that reports the contents of the power management control status register for PCI bridge support extensions. 


##### - PMCSR_BSE.AsUCHAR

Contains the same data as the <b>BridgeSupport</b> member.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_PM_CAPABILITY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

