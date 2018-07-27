---
UID: NS:miniport._PCI_CAPABILITIES_HEADER
title: "_PCI_CAPABILITIES_HEADER"
author: windows-driver-content
description: The PCI_CAPABILITIES_HEADER structure defines a header that is present in every PCI capability structure.
old-location: pci\pci_capabilities_header.htm
tech.root: PCI
ms.assetid: 6a2ee9be-03bc-436d-91c7-f00222911b19
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_CAPABILITIES_HEADER, PCI.pci_capabilities_header, PCI_CAPABILITIES_HEADER, PCI_CAPABILITIES_HEADER structure [Buses], PPCI_CAPABILITIES_HEADER, PPCI_CAPABILITIES_HEADER structure pointer [Buses], _PCI_CAPABILITIES_HEADER, pci_struct_4e7e5552-8a1b-4081-9197-df863319b01d.xml, wdm/PCI_CAPABILITIES_HEADER, wdm/PPCI_CAPABILITIES_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: miniport.h
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_CAPABILITIES_HEADER
product:
- Windows
targetos: Windows
req.typenames: PCI_CAPABILITIES_HEADER, *PPCI_CAPABILITIES_HEADER
---

# _PCI_CAPABILITIES_HEADER structure


## -description


The PCI_CAPABILITIES_HEADER structure defines a header that is present in every PCI capability structure.


## -syntax


````
typedef struct _PCI_CAPABILITIES_HEADER {
  UCHAR CapabilityID;
  UCHAR Next;
} PCI_CAPABILITIES_HEADER, *PPCI_CAPABILITIES_HEADER;
````


## -struct-fields




### -field CapabilityID

Contains an 8-bit integer that indicates the capability ID. The capability ID identifies the type of capability structure that follows this header. The <b>CapabilityID</b> member must have one of the following values:

<table>
<tr>
<th>Capability ID</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_POWER_MANAGEMENT

</td>
<td>
Indicates that the capability structure that follows the header defines a PCI power management interface. For more information about this kind of capability, see the <i>PCI Power Management Interface Specificatio</i>n.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_AGP

</td>
<td>
Indicates that the capability structure that follows the header defines the Accelerated Graphics Port (AGP) supported by the device. For more information about this kind of capability, see the <i>Accelerated Graphics Port Interface Specification.</i>

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_VPD

</td>
<td>
Indicates that the capability structure that follows the header defines Vital Product Data (VPD) features of the device.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_SLOT_ID

</td>
<td>
Indicates that the capability structure that follows the header defines external expansion capabilities of a bridge device. For more information about this kind of capability, see the <i>PCI to PCI Bridge Architecture Specificatio</i>n.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_MSI

</td>
<td>
Indicates that the capability structure that follows the header defines a <i>PCI device</i> that can do message signaled interrupt (MSI) delivery. For more information about the MSI capability, see the <i>PCI Local Bus Specification</i>.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_CPCI_HOTSWAP

</td>
<td>
Indicates that the capability structure that follows the header defines a standard interface to control and sense status. Devices that supports hot swap insertion and extraction in a CompactPCI system require this kind of interface. For more information about control and sense status in CompactPCI systems, see the <i>CompactPCI Hot Swap Specification</i>.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_PCIX

</td>
<td>
Indicates that the capability structure that follows the header defines the devices PCI-X features. For more information about PCI-X, see the <i>PCI-X Addendum to the PCI Local Bus Specification</i>.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_HYPERTRANSPORT

</td>
<td>
Indicates that the capability structure that follows the header defines control and status for devices that implement hyper transport (HT) technology links. For more information about HT technology, refer to the <i>HyperTransport I/O Link Specification</i>.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_VENDOR_SPECIFIC

</td>
<td>
Indicates that the capability structure that follows the header defines vendor specific information. For more information about how to use the capability mechanism to communicate vendor-specific information, see the <i>PCI Local Bus Specification</i>.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_DEBUG_PORT

</td>
<td>
Indicates that the capability structure that follows the header describes a debug port

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_CPCI_RES_CTRL

</td>
<td>
Indicates that the capability structure that follows the header describes CompactPCI central resource control. For more information about this kind of control see the <i>PICMG 2.13 Specification</i>.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_SHPC

</td>
<td>
Indicates that the capability structure that follows the header defines the features of a device that conforms to the standard hot-plug controller model.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_P2P_SSID

</td>
<td>
Indicates that the capability structure that follows the header defines the subsystem ID capability.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_AGP_TARGET

</td>
<td>
Indicates that the capability structure that follows the header defines the Accelerated Graphics Port (AGP) 8x capability.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_SECURE

</td>
<td>
Indicates that the capability structure that follows the header describes a secure device

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_PCI_EXPRESS

</td>
<td>
Indicates that the capability structure that follows the header defines a device that supports PCI express.

</td>
</tr>
<tr>
<td>
PCI_CAPABILITY_ID_MSIX

</td>
<td>
Indicates that the capability structure that follows the header defines an optional extension to the basic MSI functionality.

</td>
</tr>
</table>
 


### -field Next

Contains an offset into the PCI configuration space that indicates the location of the next item in the capability list. If there are no additional items in the list, this member will contain zero.


## -remarks



All PCI Capability structures have the header described by PCI_CAPABILITIES_HEADER.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a>



 

 


