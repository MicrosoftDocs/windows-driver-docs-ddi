---
UID: NS:wdm._PCI_EXPRESS_AER_CAPABILITIES
title: "_PCI_EXPRESS_AER_CAPABILITIES"
author: windows-driver-content
description: The PCI_EXPRESS_AER_CAPABILITIES structure describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_aer_capabilities.htm
old-project: PCI
ms.assetid: 7cb25991-4e82-4da2-9d1f-fadc035b25a3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_AER_CAPABILITIES, PCI.pci_express_aer_capabilities, PCI_EXPRESS_AER_CAPABILITIES, PCI_EXPRESS_AER_CAPABILITIES union [Buses], PPCI_EXPRESS_AER_CAPABILITIES, PPCI_EXPRESS_AER_CAPABILITIES union pointer [Buses], _PCI_EXPRESS_AER_CAPABILITIES, pci_struct_e316ea91-d32a-4726-ba80-8fc6bd8e3163.xml, wdm/PCI_EXPRESS_AER_CAPABILITIES, wdm/PPCI_EXPRESS_AER_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_EXPRESS_AER_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_AER_CAPABILITIES, *PPCI_EXPRESS_AER_CAPABILITIES
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_AER_CAPABILITIES structure


## -description


The PCI_EXPRESS_AER_CAPABILITIES structure describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure.


## -syntax


````
typedef union _PCI_EXPRESS_AER_CAPABILITIES {
  struct {
    ULONG FirstErrorPointer  :5;
    ULONG ECRCGenerationCapable  :1;
    ULONG ECRCGenerationEnable  :1;
    ULONG ECRCCheckCapable  :1;
    ULONG ECRCCheckEnable  :1;
    ULONG Reserved  :23;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_AER_CAPABILITIES, *PPCI_EXPRESS_AER_CAPABILITIES;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_AER_CAPABILITIES structure.


#### - ECRCCheckCapable

A single bit that indicates that the device is capable of checking ECRC.


#### - ECRCCheckEnable

A single bit that indicates that ECRC checking is enabled.


#### - ECRCGenerationCapable

A single bit that indicates that the device is capable of generating end-to-end cyclic redundancy checks (ECRC).


#### - ECRCGenerationEnable

A single bit that indicates that ECRC generation is enabled.


#### - FirstErrorPointer

The bit position of the first error that was reported in the PCIe uncorrectable error status register.


#### - Reserved

Reserved.


## -remarks



The PCI_EXPRESS_AER_CAPABILITIES structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_AER_CAPABILITIES structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_AER_CAPABILITIES union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

