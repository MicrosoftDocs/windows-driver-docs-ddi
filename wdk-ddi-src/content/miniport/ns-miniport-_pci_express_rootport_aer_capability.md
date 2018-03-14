---
UID: NS:miniport._PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
title: "_PCI_EXPRESS_ROOTPORT_AER_CAPABILITY"
author: windows-driver-content
description: The PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a root port or a root complex event collector.
old-location: pci\pci_express_rootport_aer_capability.htm
old-project: PCI
ms.assetid: 19272158-96bb-4efa-b32b-f8848d01bad1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY, PCI.pci_express_rootport_aer_capability, PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure [Buses], PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY, PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, pci_struct_f65551d3-2213-468e-aa94-508b29c11844.xml, wdm/PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, wdm/PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: miniport.h
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, *PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY
---

# _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure


## -description


The PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a root port or a root complex event collector.


## -syntax


````
typedef struct _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY {
  PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER   Header;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS   UncorrectableErrorStatus;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK     UncorrectableErrorMask;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY UncorrectableErrorSeverity;
  PCI_EXPRESS_CORRECTABLE_ERROR_STATUS     CorrectableErrorStatus;
  PCI_EXPRESS_CORRECTABLE_ERROR_MASK       CorrectableErrorMask;
  PCI_EXPRESS_AER_CAPABILITIES             CapabilitiesAndControl;
  ULONG                                    HeaderLog[4];
  PCI_EXPRESS_ROOT_ERROR_COMMAND           RootErrorCommand;
  PCI_EXPRESS_ROOT_ERROR_STATUS            RootErrorStatus;
  PCI_EXPRESS_ERROR_SOURCE_ID              ErrorSourceId;
} PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, *PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY;
````


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537466">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a> structure that describes the header for this structure.


### -field UncorrectableErrorStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537572">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.


### -field UncorrectableErrorMask

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537567">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.


### -field UncorrectableErrorSeverity

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537570">PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY</a> structure that describes the PCIe uncorrectable error severity register of the PCIe AER capability structure.


### -field CorrectableErrorStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537572">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.


### -field CorrectableErrorMask

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537567">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.


### -field CapabilitiesAndControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537456">PCI_EXPRESS_AER_CAPABILITIES</a> structure that describes the PCIe advanced error capabilities and control register of the PCIe AER capability structure.


### -field HeaderLog

An array of four 32-bit values that together contain the header for the transaction layer packet (TLP) that corresponds to a detected error.

<div class="alert"><b>Note</b>    Within each 32-bit value in the array, the bytes of the TLP are in big-endian byte order.</div>
<div> </div>

### -field RootErrorCommand

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537475">PCI_EXPRESS_ROOT_ERROR_COMMAND</a> structure that describes the PCIe root error command register of the PCIe AER capability structure.


### -field RootErrorStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537476">PCI_EXPRESS_ROOT_ERROR_STATUS</a> structure that describes the PCIe root error status register of the PCIe AER capability structure.


### -field ErrorSourceId

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537467">PCI_EXPRESS_ERROR_SOURCE_ID</a> structure that describes the PCIe error source identification register of the PCIe AER capability structure.


## -remarks



The PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

PCIe bridge devices use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure instead of the PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

All other PCIe devices and ports that are not root ports or root complex event collectors use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a> structure instead of the PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

For additional information about the PCIe advanced error reporting capability structure, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537462">PCI_EXPRESS_CORRECTABLE_ERROR_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537475">PCI_EXPRESS_ROOT_ERROR_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537461">PCI_EXPRESS_CORRECTABLE_ERROR_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537476">PCI_EXPRESS_ROOT_ERROR_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537466">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537456">PCI_EXPRESS_AER_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537572">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537467">PCI_EXPRESS_ERROR_SOURCE_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537570">PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537567">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a>



 

 


