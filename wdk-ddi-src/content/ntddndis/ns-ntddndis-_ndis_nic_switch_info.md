---
UID: NS:ntddndis._NDIS_NIC_SWITCH_INFO
title: _NDIS_NIC_SWITCH_INFO (ntddndis.h)
description: The NDIS_NIC_SWITCH_INFO structure specifies the information about a network adapter switch on a network adapter.
old-location: netvista\ndis_nic_switch_info.htm
tech.root: netvista
ms.assetid: 0da6927f-c940-4e46-a63a-2127bd7fa63d
ms.date: 05/02/2018
keywords: ["NDIS_NIC_SWITCH_INFO structure"]
ms.keywords: "*PNDIS_NIC_SWITCH_INFO, NDIS_NIC_SWITCH_INFO, NDIS_NIC_SWITCH_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_INFO, PNDIS_NIC_SWITCH_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_INFO, netvista.ndis_nic_switch_info, ntddndis/NDIS_NIC_SWITCH_INFO, ntddndis/PNDIS_NIC_SWITCH_INFO"
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
req.typenames: NDIS_NIC_SWITCH_INFO, *PNDIS_NIC_SWITCH_INFO
f1_keywords:
 - _NDIS_NIC_SWITCH_INFO
 - ntddndis/_NDIS_NIC_SWITCH_INFO
 - PNDIS_NIC_SWITCH_INFO
 - ntddndis/PNDIS_NIC_SWITCH_INFO
 - NDIS_NIC_SWITCH_INFO
 - ntddndis/NDIS_NIC_SWITCH_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_NIC_SWITCH_INFO
---

# _NDIS_NIC_SWITCH_INFO structure


## -description

The <b>NDIS_NIC_SWITCH_INFO</b> structure specifies the information about a network adapter switch on a network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_INFO</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_INFO_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_INFO_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise OR of configuration flags that are enabled on the switch.

<div class="alert"><b>Note</b>  For NDIS 6.30, no configuration flags are defined for the switch. The <b>Flags</b> member must be set to zero.</div>
<div> </div>

### -field SwitchType

An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_nic_switch_type">NDIS_NIC_SWITCH_TYPE</a> value that specifies the type of the switch.

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field SwitchFriendlyName

An NDIS_NIC_SWITCH_FRIENDLY_NAME value that contains the user-friendly description of the switch.

### -field NumVFs

A ULONG value that specifies the number of PCI Express (PCIe) Virtual Functions (VFs) that are enabled on the network adapter. Enabled VFs can be in either an allocated or unallocated state.

### -field NumAllocatedVFs

A ULONG value that specifies the number of VFs that have been allocated on the network adapter switch specified by <b>SwitchId</b>. VFs are allocated  through OID set requests of <a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>.

### -field NumVPorts

A ULONG value that specifies the  number of virtual ports (VPorts) that are configured on the network adapter switch specified by <b>SwitchId</b>.

This ULONG value is the sum of the following:

<ul>
<li>The maximum number of VPorts that can be created through OID set requests of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>.</li>
<li>The default VPort attached to the Physical Function (PF).</li>
</ul>

### -field NumActiveVPorts

A ULONG value that specifies the number of VPorts that have been created on the network adapter switch specified by <b>SwitchId</b>. 

<div class="alert"><b>Note</b>  This ULONG value includes the default VPort, in addition to the nondefault VPorts created through OID set requests of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>.</div>
<div> </div>

### -field NumQueuePairsForDefaultVPort

A ULONG value that specifies the number of queue pairs allocated for the default VPort.  The  default VPort is always attached to the PF.

A queue pair consists of a transmit queue and receive queue. The miniport driver associates one or more queue pairs with the default VPort at the time of switch creation through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-switch">OID_NIC_SWITCH_CREATE_SWITCH</a>. 

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, there can only be one queue pair that can be configured for the default VPort.</div>
<div> </div>

### -field NumQueuePairsForNonDefaultVPorts

A ULONG value that specifies the number of queue pairs allocated for the nondefault VPorts. A nondefault VPort can be attached to either the PF or any VF of the network adapter.

The miniport driver associates one or more queue pairs with a nondefault VPort through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>.

### -field NumActiveDefaultVPortMacAddresses

A ULONG value that specifies the number of unicast MAC address filters that are currently set on the default VPort that is attached to the PF of the network adapter.

### -field NumActiveNonDefaultVPortMacAddresses

A ULONG value that specifies the number of unicast MAC address filters that are currently set on nondefault VPorts.

### -field NumActiveDefaultVPortVlanIds

A ULONG value that specifies the number of virtual local area network (VLAN) identifier filters that are currently set on the default VPort.

### -field NumActiveNonDefaultVPortVlanIds

A ULONG value that specifies the number of VLAN identifier filters that are currently set on the nondefault VPorts.

## -remarks

The <b>NDIS_NIC_SWITCH_INFO</b> structure is used in OID query requests of <a href="/windows-hardware/drivers/network/oid-nic-switch-enum-switches">OID_NIC_SWITCH_ENUM_SWITCHES</a>. This OID request is used to enumerate the network adapter switches on a network adapter. When this OID request is issued, one or more <b>NDIS_NIC_SWITCH_INFO</b> structures are returned within an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info_array">NDIS_NIC_SWITCH_INFO_ARRAY</a> structure.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, only the <b>NDIS_NIC_SWITCH_INFO</b> that describes the information about the default network adapter switch is returned through an OID request of <a href="/windows-hardware/drivers/network/oid-nic-switch-enum-switches">OID_NIC_SWITCH_ENUM_SWITCHES</a>.</div>
<div> </div>
An <b>NDIS_NIC_SWITCH_INFO</b> structure contains information about a network adapter switch that was previously created through an OID method request of OID_NIC_SWITCH_CREATE_SWITCH. 

For more information about the SR-IOV interface, see 	<a href="/windows-hardware/drivers/network/overview-of-single-root-i-o-virtualization--sr-iov-">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info_array">NDIS_NIC_SWITCH_INFO_ARRAY</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-create-switch">OID_NIC_SWITCH_CREATE_SWITCH</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>