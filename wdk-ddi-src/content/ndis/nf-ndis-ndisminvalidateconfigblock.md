---
UID: NF:ndis.NdisMInvalidateConfigBlock
title: NdisMInvalidateConfigBlock function
author: windows-driver-content
description: A miniport driver calls the NdisMInvalidateConfigBlock function to notify NDIS that the data for one or more Virtual Function (VF) configuration blocks has been changed.
old-location: netvista\ndisminvalidateconfigblock.htm
old-project: netvista
ms.assetid: 26D07A41-C431-41F1-9F5E-880B48CC2F0B
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMInvalidateConfigBlock, NdisMInvalidateConfigBlock function [Network Drivers Starting with Windows Vista], ndis/NdisMInvalidateConfigBlock, netvista.ndisminvalidateconfigblock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMInvalidateConfigBlock
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMInvalidateConfigBlock function


## -description


A miniport driver calls the <b>NdisMInvalidateConfigBlock</b> function to notify NDIS that the data for one or more Virtual Function (VF) configuration blocks has been changed.
<div class="alert"><b>Note</b>  <b>NdisMInvalidateConfigBlock</b> must only be called by the miniport driver for the network adapter's PCIe Physical Function (PF).</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param VFId [in]

The identifier of the VF for which the device location is returned.


### -param BlockMask [in]

A ULONGLONG value that specifies a bitmask for the first 64 VF configuration blocks. Each bit in the bitmask corresponds to a VF configuration block. If the bit is set to one, the data associated with the corresponding VF configuration block has changed.



## -returns




     None.




## -remarks



A VF configuration block is used for backchannel communication between the PF and VF miniport drivers. The IHV can define one or more VF configuration blocks for the device. Each VF configuration block has an IHV-defined format, length,  and block ID.

<div class="alert"><b>Note</b>  Data from each VF configuration block is  used only by the PF and VF miniport drivers.

</div>
<div> </div>
VF configuration data is exchanged between the following drivers:

<ul>
<li>
The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
In order to handle notifications of invalid VF configuration data, NDIS and the miniport drivers perform the following steps:

<ol>
<li>
In the guest operating system, NDIS issues an I/O control request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request. When this IOCTL is completed, NDIS is notified that VF configuration data has changed.

</li>
<li>
In the management operating system, the following steps occur:<ol>
<li>The PF miniport driver calls the <b>NdisMInvalidateConfigBlock</b> function to notify NDIS that VF configuration data has changed and is no longer valid. </li>
<li>
NDIS signals the virtualization stack, which runs in the management operating system, about the change to VF configuration block data. The virtualization stack caches the <i>BlockMask</i> parameter data. 

<div class="alert"><b>Note</b>  Each time that the PF miniport driver calls <b>NdisMInvalidateConfigBlock</b>, the virtualization  stack ORs the <i>BlockMask</i> parameter data with the current value in its cache.</div>
<div> </div>
</li>
<li>
The virtualization stack notifies the virtual PCI (VPCI) driver, which  runs in the guest operating system, about the invalidation of VF configuration data.  The virtualization stack sends the cached <i>BlockMask</i> parameter data to the VPCI driver.

</li>
</ol>


</li>
<li>
In the guest operating system, the following steps occur:<ol>
<li>
The VPCI driver saves the cached <i>BlockMask</i> parameter data in the <b>BlockMask</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451586">VPCI_INVALIDATE_BLOCK_OUTPUT</a> structure that is associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request.

</li>
<li>
The VPCI driver successfully completes  the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request. When this happens, NDIS issues an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a>  to the VF miniport driver. An <a href="https://msdn.microsoft.com/library/windows/hardware/hh451684">NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</a> request is passed along in the OID request. This structure contains the cached <i>BlockMask</i> parameter data.

NDIS also issues another <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request to handle successive notifications of changes to VF configuration data.

</li>
<li>
When the VF driver handles the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a> request, it reads data from the specified VF configuration blocks.

</li>
</ol>


</li>
</ol>
For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://msdn.microsoft.com/66D40452-1286-449E-BD6B-AFAD466E03A1">SR-IOV PF/VF Backchannel Communication</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451684">NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451879">OID_SRIOV_READ_VF_CONFIG_SPACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451586">VPCI_INVALIDATE_BLOCK_OUTPUT</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMInvalidateConfigBlock function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
