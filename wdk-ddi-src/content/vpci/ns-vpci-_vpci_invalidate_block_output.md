---
UID: NS:vpci._VPCI_INVALIDATE_BLOCK_OUTPUT
title: "_VPCI_INVALIDATE_BLOCK_OUTPUT"
author: windows-driver-content
description: The VPCI_INVALIDATE_BLOCK_OUTPUT structure is used in an IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request.
old-location: kernel\vpci_invalidate_block_output.htm
tech.root: pci
ms.assetid: 6971C724-CE5E-44BC-8D3A-FAD248771E6F
ms.date: 4/30/2018
ms.keywords: "*PVPCI_INVALIDATE_BLOCK_OUTPUT, PVPCI_INVALIDATE_BLOCK_OUTPUT, PVPCI_INVALIDATE_BLOCK_OUTPUT structure pointer [Kernel-Mode Driver Architecture], VPCI_INVALIDATE_BLOCK_OUTPUT, VPCI_INVALIDATE_BLOCK_OUTPUT structure [Kernel-Mode Driver Architecture], _VPCI_INVALIDATE_BLOCK_OUTPUT, kernel.vpci_invalidate_block_output, vpci/PVPCI_INVALIDATE_BLOCK_OUTPUT, vpci/VPCI_INVALIDATE_BLOCK_OUTPUT"
ms.topic: struct
req.header: vpci.h
req.include-header: Vpci.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Vpci.h
api_name:
-	VPCI_INVALIDATE_BLOCK_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: VPCI_INVALIDATE_BLOCK_OUTPUT, *PVPCI_INVALIDATE_BLOCK_OUTPUT
---

# _VPCI_INVALIDATE_BLOCK_OUTPUT structure


## -description


The <b>VPCI_INVALIDATE_BLOCK_OUTPUT</b> structure is used in an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request.

The driver for a PCI Express (PCIe) virtual function (VF) issues the <b>IOCTL_VPCI_INVALIDATE_BLOCK</b> IOCTL request in order be notified of changes to data in one or more VF configuration blocks. When the IOCTL request is completed, the <b>VPCI_INVALIDATE_BLOCK_OUTPUT</b> structure specifies which VF configuration blocks have been changed.
<div class="alert"><b>Note</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request is issued by the driver of a PCIe  VF on a device that supports the single root I/O virtualization (SR-IOV) interface.</div><div> </div>

## -struct-fields




### -field BlockMask

A <b>UINT64</b> value that specifies a bitmask for the first 64 VF configuration blocks. Each bit in the bitmask corresponds to a VF configuration block. If a bit is set to one, the data associated with the corresponding VF configuration block has changed.


## -remarks



A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

<ul>
<li>
The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.

</li>
<li>
The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the drivers of the PF and VF.

However, we recommend that IHVs reserve the first 64 VF configuration blocks for data that may change occasionally. </div>
<div> </div>



## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a>
 

 

