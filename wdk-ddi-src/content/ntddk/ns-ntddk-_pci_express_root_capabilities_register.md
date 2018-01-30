---
UID: NS:ntddk._PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
title: "_PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) root capabilities register of a PCIe capability structure.
old-location: pci\pci_express_root_capabilities_register.htm
old-project: PCI
ms.assetid: d4e6cc35-f6f1-4983-b4d6-2a524245fd15
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: pci_struct_5b1d9283-10c9-40dc-8dc2-552ab7a2cab5.xml, *PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, ntddk/PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PCI.pci_express_root_capabilities_register, _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, ntddk/PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER union pointer [Buses], PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER union [Buses], PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
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
-	PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER"
---

# _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure


## -description


The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) root capabilities register of a PCIe capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER {
  struct {
    USHORT CRSSoftwareVisibility  :1;
    USHORT Rsvd  :15;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER, *PPCI_EXPRESS_ROOT_CAPABILITIES_REGISTER;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.CRSSoftwareVisibility

 


### -field DUMMYSTRUCTNAME.Rsvd

 


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure.


#### - CRSSoftwareVisibility

A single bit that indicates that the root port is capable of returning configuration request retry status (CRS) completion status to software.


#### - Rsvd

Reserved.


## -remarks


The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

