---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VF_INFO
title: _NDIS_NIC_SWITCH_VF_INFO (ntddndis.h)
description: The NDIS_NIC_SWITCH_VF_INFO structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter.
old-location: netvista\ndis_nic_switch_vf_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_NIC_SWITCH_VF_INFO structure"]
ms.keywords: "*PNDIS_NIC_SWITCH_VF_INFO, NDIS_NIC_SWITCH_VF_INFO, NDIS_NIC_SWITCH_VF_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VF_INFO, PNDIS_NIC_SWITCH_VF_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VF_INFO, netvista.ndis_nic_switch_vf_info, ntddndis/NDIS_NIC_SWITCH_VF_INFO, ntddndis/PNDIS_NIC_SWITCH_VF_INFO"
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
req.irql: 
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VF_INFO, *PNDIS_NIC_SWITCH_VF_INFO
f1_keywords:
 - _NDIS_NIC_SWITCH_VF_INFO
 - ntddndis/_NDIS_NIC_SWITCH_VF_INFO
 - PNDIS_NIC_SWITCH_VF_INFO
 - ntddndis/PNDIS_NIC_SWITCH_VF_INFO
 - NDIS_NIC_SWITCH_VF_INFO
 - ntddndis/NDIS_NIC_SWITCH_VF_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_NIC_SWITCH_VF_INFO
---

# _NDIS_NIC_SWITCH_VF_INFO structure


## -description

The <b>NDIS_NIC_SWITCH_VF_INFO</b> structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_INFO</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VF_INFO_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VF_INFO_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field VMName

An NDIS_VM_NAME value that specifies the name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.

<div class="alert"><b>Note</b>  The Hyper-V child partition is also known as a virtual machine (VM).</div>
<div> </div>

### -field VMFriendlyName

An NDIS_VM_FRIENDLYNAME value that specifies the external name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.

### -field NicName

An NDIS_SWITCH_NIC_NAME value that specifies the name of the virtual machine (VM) network adapter. This member contains the user-friendly description of the network adapter.



The VM network adapter is a virtual device that is exposed in the guest operating system that runs in a Hyper-V child partition. The VM network adapter teams with the VF network adapter to provide the hardware-based VF data path over the SR-IOV interface. 

For more information about the VF data path, see <a href="/windows-hardware/drivers/network/sr-iov-vf-data-path">SR-IOV VF Data Path</a>.

### -field MacAddressLength

A USHORT value that specifies the length of the <b>PermanentMacAddress</b> and <b>CurrentMacAddress</b> members.

### -field PermanentMacAddress

The permanent MAC address of the VF. This is the permanent MAC address for the VF network adapter that is exposed in the guest operating system.

### -field CurrentMacAddress

The current MAC address of the VF. This is the current MAC address for the VF network adapter that is exposed in the guest operating system.

### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

### -field RequestorId

An NDIS_VF_RID that specifies the PCI Express (PCIe) Requestor ID (RID) of the VF.

## -remarks

An <b>NDIS_NIC_SWITCH_VF_INFO</b> structure contains information about a VF that was previously created through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>. When this OID request is issued, one or more <b>NDIS_NIC_SWITCH_VF_INFO</b> structures are returned within an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vf_info_array">NDIS_NIC_SWITCH_VF_INFO_ARRAY</a> structure.

For more information about the SR-IOV interface, see 	<a href="/windows-hardware/drivers/network/overview-of-single-root-i-o-virtualization--sr-iov-">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vf_info_array">NDIS_NIC_SWITCH_VF_INFO_ARRAY</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>
