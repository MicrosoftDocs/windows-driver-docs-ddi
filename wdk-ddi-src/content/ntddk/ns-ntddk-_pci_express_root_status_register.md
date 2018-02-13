---
UID: NS:ntddk._PCI_EXPRESS_ROOT_STATUS_REGISTER
title: "_PCI_EXPRESS_ROOT_STATUS_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_ROOT_STATUS_REGISTER structure describes a PCI Express (PCIe) root status register of a PCIe capability structure.
old-location: pci\pci_express_root_status_register.htm
old-project: PCI
ms.assetid: e7f6a8b9-22f1-4c5b-a0b7-b87ceb2c0b1b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: ntddk/PCI_EXPRESS_ROOT_STATUS_REGISTER, *PPCI_EXPRESS_ROOT_STATUS_REGISTER, PPCI_EXPRESS_ROOT_STATUS_REGISTER, PCI_EXPRESS_ROOT_STATUS_REGISTER union [Buses], PPCI_EXPRESS_ROOT_STATUS_REGISTER union pointer [Buses], PCI_EXPRESS_ROOT_STATUS_REGISTER, pci_struct_ff3a211f-421b-41f3-9250-d658636bfe49.xml, PCI.pci_express_root_status_register, _PCI_EXPRESS_ROOT_STATUS_REGISTER, ntddk/PPCI_EXPRESS_ROOT_STATUS_REGISTER
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PCI_EXPRESS_ROOT_STATUS_REGISTER
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_ROOT_STATUS_REGISTER, PCI_EXPRESS_ROOT_STATUS_REGISTER"
---

# _PCI_EXPRESS_ROOT_STATUS_REGISTER structure


## -description


The PCI_EXPRESS_ROOT_STATUS_REGISTER structure describes a PCI Express (PCIe) root status register of a PCIe capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_ROOT_STATUS_REGISTER {
  struct {
    ULONG PMERequestorId  :16;
    ULONG PMEStatus  :1;
    ULONG PMEPending  :1;
    ULONG Rsvd  :14;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_ROOT_STATUS_REGISTER, *PPCI_EXPRESS_ROOT_STATUS_REGISTER;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.PMERequestorId

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537471">PCI_EXPRESS_PME_REQUESTOR_ID</a> structure that describes the power management event (PME) requester identifier of the last PME requester.


### -field DUMMYSTRUCTNAME.PMEStatus

A single bit that indicates that a power management event (PME) was asserted by the requester identified by the <b>PMERequestorId</b> member.


### -field DUMMYSTRUCTNAME.PMEPending

A single bit that indicates that another power management event (PME) is pending while the <b>PMEStatus</b> bit is set.


### -field DUMMYSTRUCTNAME.Rsvd

Reserved.


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_ROOT_STATUS_REGISTER structure.


## -remarks



The PCI_EXPRESS_ROOT_STATUS_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_STATUS_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537471">PCI_EXPRESS_PME_REQUESTOR_ID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ROOT_STATUS_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

