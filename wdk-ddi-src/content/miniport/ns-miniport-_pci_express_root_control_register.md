---
UID: NS:miniport._PCI_EXPRESS_ROOT_CONTROL_REGISTER
title: "_PCI_EXPRESS_ROOT_CONTROL_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) root control register of a PCIe capability structure.
old-location: pci\pci_express_root_control_register.htm
old-project: PCI
ms.assetid: 0f2c321c-f03b-4655-bbd1-25fcc6c52cfa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI.pci_express_root_control_register, PCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI_EXPRESS_ROOT_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PPCI_EXPRESS_ROOT_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_ROOT_CONTROL_REGISTER, ntddk/PCI_EXPRESS_ROOT_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_ROOT_CONTROL_REGISTER, pci_struct_ef335e30-c046-4066-8411-27bf96cbcd08.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PCI_EXPRESS_ROOT_CONTROL_REGISTER
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_ROOT_CONTROL_REGISTER, *PPCI_EXPRESS_ROOT_CONTROL_REGISTER
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




### -field DUMMYSTRUCTNAME

 


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_ROOT_CONTROL_REGISTER structure.


#### - CRSSoftwareVisibilityEnable

A single bit that indicates that the root port is enabled to return configuration request retry status (CRS) completion status to software.


#### - CorrectableSerrEnable

A single bit that indicates that a system error should be generated if a correctable error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


#### - FatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


#### - NonFatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


#### - PMEInterruptEnable

A single bit that indicates that interrupts are enabled for power management events.


#### - Rsvd

Reserved.


## -remarks



The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_CONTROL_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ROOT_CONTROL_REGISTER union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

