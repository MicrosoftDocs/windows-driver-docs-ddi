---
UID: NS:ntddndis._NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO
title: "_NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO"
author: windows-driver-content
description: The NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure specifies one or more Virtual Function (VF) configuration blocks whose data has been changed (invalidated) by the driver for the PCI Express (PCIe) Physical Function (PF) on the network adapter.
old-location: netvista\ndis_sriov_vf_invalidate_config_block_info.htm
old-project: netvista
ms.assetid: 29FA9E0E-9DE4-459C-9947-3FD232E6417B
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO, NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO, NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO, PNDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO, netvista.ndis_sriov_vf_invalidate_config_block_info, ntddndis/NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO, ntddndis/PNDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO, *PNDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO
---

# _NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure


## -description



The <b>NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</b> structure specifies one or more Virtual Function (VF) configuration blocks whose data has been changed (<i>invalidated</i>) by the driver for the PCI Express (PCIe) Physical Function (PF) on the network adapter.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</b> structure, the miniport driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SIZEOF_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_VF_CONFIG_STATE_REVISION_1.


### -field BlockMask

A ULONG64 value that specifies a bitmask for the first 64 VF configuration blocks. Each bit in the bitmask corresponds to a VF configuration block. If the bit is set to one, the data associated with the corresponding VF configuration block has changed.



## -remarks



The  <b>NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a>.

A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

<ul>
<li>
The VF miniport driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF miniport driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the PF and VF miniport drivers.

However, we recommend that IHVs reserve the first 64 VF configuration blocks for data that may change occasionally. </div>
<div> </div>
For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://msdn.microsoft.com/66D40452-1286-449E-BD6B-AFAD466E03A1">SR-IOV PF/VF Backchannel Communication</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

