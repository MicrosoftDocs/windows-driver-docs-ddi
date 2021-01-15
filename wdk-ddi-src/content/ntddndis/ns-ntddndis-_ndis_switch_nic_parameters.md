---
UID: NS:ntddndis._NDIS_SWITCH_NIC_PARAMETERS
title: _NDIS_SWITCH_NIC_PARAMETERS (ntddndis.h)
description: The NDIS_SWITCH_NIC_PARAMETERS structure specifies the configuration parameters for a network adapter (NIC) that is connected to a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_nic_parameters.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_NIC_PARAMETERS structure"]
ms.keywords: "*PNDIS_SWITCH_NIC_PARAMETERS, NDIS_SWITCH_NIC_FLAGS_NIC_INITIALIZING, NDIS_SWITCH_NIC_PARAMETERS, NDIS_SWITCH_NIC_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_NIC_PARAMETERS, PNDIS_SWITCH_NIC_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_NIC_PARAMETERS, netvista.ndis_switch_nic_parameters, ntddndis/NDIS_SWITCH_NIC_PARAMETERS, ntddndis/PNDIS_SWITCH_NIC_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
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
req.typenames: NDIS_SWITCH_NIC_PARAMETERS, *PNDIS_SWITCH_NIC_PARAMETERS
f1_keywords:
 - _NDIS_SWITCH_NIC_PARAMETERS
 - ntddndis/_NDIS_SWITCH_NIC_PARAMETERS
 - PNDIS_SWITCH_NIC_PARAMETERS
 - ntddndis/PNDIS_SWITCH_NIC_PARAMETERS
 - NDIS_SWITCH_NIC_PARAMETERS
 - ntddndis/NDIS_SWITCH_NIC_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - _NDIS_SWITCH_NIC_PARAMETERS
 - PNDIS_SWITCH_NIC_PARAMETERS
 - NDIS_SWITCH_NIC_PARAMETERS
---

# _NDIS_SWITCH_NIC_PARAMETERS structure


## -description

The <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure specifies the configuration parameters for a network adapter (NIC) that is connected to a Hyper-V extensible switch port.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_NIC_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_SWITCH_NIC_PARAMETERS_REVISION_1</b>.

### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. The following flag value is defined.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_SWITCH_NIC_FLAGS_NIC_INITIALIZING"></a><a id="ndis_switch_nic_flags_nic_initializing"></a><dl>
<dt><b>NDIS_SWITCH_NIC_FLAGS_NIC_INITIALIZING</b></dt>
</dl>
</td>
<td width="60%">
This flag is set when the <a href="/windows-hardware/drivers/network/oid-switch-nic-create">OID_SWITCH_NIC_CREATE</a> OID is issued for the first time in the lifetime of a VM NIC object. If this flag is set:

<ul>
<li>A Hyper-V Extensible Switch extension can optionally reduce the value of the <b>MTU</b> member in the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure if it needs to reserve headroom for encapsulation before it passes the OID down the stack. The extension will not be able to reserve encapsulation headroom for any other type of NIC.</li>
<li>The extension should not increase the <b>MTU</b> value.</li>
</ul>
  This flag will be set only if the <b>NicType</b> member is <b>NdisSwitchNicTypeSynthetic</b>.

</td>
</tr>
</table>

### -field NicName

 An NDIS_SWITCH_NIC_NAME value that specifies the unique internal name of the network adapter that is connected to an extensible switch port. 

For more information, see the Remarks section.

### -field NicFriendlyName

 An NDIS_SWITCH_NIC_FRIENDLYNAME value that specifies the user-friendly description of the network adapter.

### -field PortId

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port to which the network adapter is connected.

### -field NicIndex

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the  extensible switch port specified by the <b>PortId</b> member.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="/windows-hardware/drivers/network/network-adapter-index-values">Network Adapter Index Values</a>.

### -field NicType

An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_nic_type">NDIS_SWITCH_NIC_TYPE</a> value that specifies the type of the network adapter that is connected to an extensible switch port.

### -field NicState

An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_nic_state">NDIS_SWITCH_NIC_STATE</a> value that specifies the current state of the network adapter.

### -field VmName

An NDIS_VM_NAME value that specifies the unique internal name of the Hyper-V child partition in which the guest operating system that exposes the network adapter is running.



The Hyper-V child partition is also known as a virtual machine (VM).

<div class="alert"><b>Note</b>  This member is valid only if the <b>NicType</b> member contains a value of <b>NdisSwitchNicSyntheticNic</b> or <b>NdisSwitchNicEmulatedNic.</b></div>
<div> </div>

### -field VmFriendlyName

### -field NetCfgInstanceId

A GUID value that specifies the <b>NetCfgInstanceId</b> registry value of the
underlying network adapter.

<div class="alert"><b>Note</b>  This member is valid only if the <b>NicType</b> member is set to <b>NdisSwitchNicTypeExternal</b> or <b>NdisSwitchNicTypeInternal</b>.  <b>NetCfgInstanceId</b> will not be valid until after the virtual network adapter has been initialized.</div>
<div> </div>

### -field MTU

A <b>ULONG</b> value that specifies the maximum transmission unit (MTU) size, in bytes, for the network adapter.

<div class="alert"><b>Note</b>  The value of this member can change during the lifetime of a VM NIC. Therefore, extensions should read this member of the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure that is passed down with the following OIDs:<ul>
<li>
<a href="/windows-hardware/drivers/network/oid-switch-nic-connect">OID_SWITCH_NIC_CONNECT</a>
</li>
<li>
<a href="/windows-hardware/drivers/network/oid-switch-nic-updated">OID_SWITCH_NIC_UPDATED</a>
</li>
</ul>
</div>
<div> </div>

### -field NumaNodeId

A <b>USHORT</b> value that specifies the identifier for the preferred Non-Uniform Memory Access (NUMA) node of a CPU. On computers that support NUMA architecture, the preferred NUMA node is the CPU that has the smallest distance to the network adapter.



<div class="alert"><b>Note</b>  This member is valid only if the <b>NicType</b> member is set to <b>NdisSwitchNicTypeSynthetic</b> or <b>NdisSwitchNicTypeEmulated</b>.</div>
<div> </div>

### -field PermanentMacAddress

A <b>UCHAR</b> array that specifies the media access control (MAC) address as configured on the host partition for  the network adapter. This can be different from the MAC address currently in use by the network adapter.

### -field VMMacAddress

A <b>UCHAR</b> array that specifies the MAC address that is configured on the network adapter inside the VM itself. The field is all zeros for non VM NICs. If <i>AllowMacSpoofing</i> (from <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_security">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>) is TRUE, this address will also be applied to the <i>CurrentMacAddress.</i>

### -field CurrentMacAddress

A <b>UCHAR</b> array that specifies the MAC address that is currently being used in the switch for the network adapter. If <i>AllowMacSpoofing</i> and <i>AllowTeaming</i> are both FALSE, then this value will be equal to <i>PermanentMacAddress</i>. If <i>AllowMacSpoofing</i> is TRUE, this value will be equal to the <i>VMMacAddress</i>. If <i>AllowTeaming</i> is TRUE and teaming failover has occurred inside the VM, the <i>CurrentMacAddress</i> will be equal to the MAC address that was failed over to the network adapter or <i>PermanentMacAddress</i> if no failover has occurred.

### -field VFAssigned

A <b>BOOLEAN</b> value that, if set to <b>TRUE</b>, specifies that the network adapter is attached to a PCI Express (PCIe) virtual function (VF). A VF is exposed by an underlying physical network adapter that supports the single root I/O virtualization (SR-IOV) interface.

For more information, see the Remarks section.

<div class="alert"><b>Note</b>  The <b>VFAssigned</b> member is valid only if the <b>NicType</b> member contains a value of <b>NdisSwitchNicTypeEmulated</b> or <b>NdisSwitchNicTypeSynthetic</b>. This member must be set to <b>FALSE</b> if the <b>NicType</b> member contains a value of <b>NdisSwitchNicTypeExternal</b> or <b>NdisSwitchNicTypeInternal</b>.</div>
<div> </div>

### -field NdisReserved

 




#### - VMFriendlyName

An NDIS_VM_FRIENDLYNAME value that specifies the external name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.

## -remarks

OID query requests of <a href="/windows-hardware/drivers/network/oid-switch-nic-array">OID_SWITCH_NIC_ARRAY</a> return an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_array">NDIS_SWITCH_NIC_ARRAY</a> structure that contains zero or more elements. Each element is formatted as an <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure.

The <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure is also used in the following OID requests: 

<ul>
<li>

<a href="/windows-hardware/drivers/network/oid-switch-nic-create">OID_SWITCH_NIC_CREATE</a>


</li>
<li>

<a href="/windows-hardware/drivers/network/oid-switch-nic-connect">OID_SWITCH_NIC_CONNECT</a>


</li>
<li>

<a href="/windows-hardware/drivers/network/oid-switch-nic-updated">OID_SWITCH_NIC_UPDATED</a>


</li>
<li>

<a href="/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a>


</li>
<li>

<a href="/windows-hardware/drivers/network/oid-switch-nic-disconnect">OID_SWITCH_NIC_DISCONNECT</a>


</li>
</ul>
<div class="alert"><b>Note</b>  The <b>NDIS_SWITCH_NIC_NAME</b>,  <b>NDIS_SWITCH_NIC_FRIENDLYNAME</b>, <b>NDIS_VM_NAME</b>, and  <b>NDIS_VM_FRIENDLYNAME</b> data types are type-defined by the <a href="/windows/win32/api/ifdef/ns-ifdef-if_counted_string_lh">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character.

</div>
<div> </div>
<h3><a id="Guidelines_for_the_NicType_and_NicName_Members"></a><a id="guidelines_for_the_nictype_and_nicname_members"></a><a id="GUIDELINES_FOR_THE_NICTYPE_AND_NICNAME_MEMBERS"></a>Guidelines for the <b>NicType</b> and <b>NicName</b> Members</h3>
 Based on the value <b>NicType</b> member, the format of the <b>NicName</b> member is as follows:

<ul>
<li>
If the <b>NicType</b> member is set to <b>NdisSwitchNicTypeExternal</b>, the value of the <b>NicName</b> member is the unique instance identifier (<b>InstanceId</b>) of the physical network adapter that is bound to the external network adapter. This type of  network adapter is exposed in the management operating system that runs in the Hyper-V parent partition.


The external network adapter provides a connection to the  physical network interface that is available on the host. The external network adapter can be accessed by the Hyper-V parent partition and all child partitions.

<div class="alert"><b>Note</b>  The <b>InstanceId</b> value is generated by the <a href="/windows-hardware/drivers/install/pnp-manager">Plug and Play manager</a> that runs in the management operating system.</div>
<div> </div>
</li>
<li>
If the <b>NicType</b> member is set to <b>NdisSwitchNicTypeInternal</b>, the value of the <b>NicName</b> member is the device display name that identifies the internal  network adapter. This type of network adapter is exposed in the management operating system of a Hyper-V parent partition.


The internal network adapter can be accessed by the Hyper-V parent partition and all child partitions. However, the internal network adapter does not connect to the physical network interface that is available on the host.

<div class="alert"><b>Note</b>  The device display name is generated by the Hyper-V WMI management layer that runs in the management operating system.</div>
<div> </div>
</li>
<li>
For all other <b>NicType</b> member values, the value of the <b>NicName</b> member is uniquely assigned to the synthetic or emulated network adapter by the policy management interface.
These types of network adapters are exposed in the guest operating system that runs is a Hyper-V child partition.

</li>
</ul>
<h3><a id="Guidelines_for_the_VFAssigned_Member"></a><a id="guidelines_for_the_vfassigned_member"></a><a id="GUIDELINES_FOR_THE_VFASSIGNED_MEMBER"></a>Guidelines for the <b>VFAssigned</b> Member</h3>
A PCIe VF is created and allocated by an underlying physical adapter that supports the SR-IOV interface. After the PCIe VF is created, the virtualization stack attaches, or <i>assigns</i>,  a Hyper-V child partition to the VF. The guest operating system that runs in this partition exposes a virtual machine (VM) network adapter that is attached, or <i>assigned</i> to the underlying SR-IOV physical adapter.

If the <b>VFAssigned</b> member is set to <b>TRUE</b>, packets are routed directly between the underlying SR-IOV physical network adapter and the virtual adapter. However, because the extensible switch is not involved in packet delivery, extensible switch port policies, such as access control lists (ACLs), are not applied to these packets.

The extension can remove a VF assignment by issuing an <a href="/windows-hardware/drivers/network/ndis-status-switch-port-remove-vf">NDIS_STATUS_SWITCH_PORT_REMOVE_VF</a> status indication. This indication causes the packets to be delivered through an extensible switch port instead of directly between the VM network adapter and the SR-IOV physical adapter. This allows the extensible switch port policies to be applied to packets that are received or sent over the extensible switch port. When the extension makes the <b>NDIS_STATUS_SWITCH_PORT_REMOVE_VF</b> status indication, it specifies which extensible switch port the virtual network adapter is connected to.

For more information, see <a href="/windows-hardware/drivers/network/ndis-status-switch-port-remove-vf">NDIS_STATUS_SWITCH_PORT_REMOVE_VF</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/ndis-status-switch-port-remove-vf">NDIS_STATUS_SWITCH_PORT_REMOVE_VF</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_array">NDIS_SWITCH_NIC_ARRAY</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_nic_state">NDIS_SWITCH_NIC_STATE</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_nic_type">NDIS_SWITCH_NIC_TYPE</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-array">OID_SWITCH_NIC_ARRAY</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-connect">OID_SWITCH_NIC_CONNECT</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-create">OID_SWITCH_NIC_CREATE</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-delete">OID_SWITCH_NIC_DELETE</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-disconnect">OID_SWITCH_NIC_DISCONNECT</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-save">OID_SWITCH_NIC_SAVE</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-save-complete">OID_SWITCH_NIC_SAVE_COMPLETE</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-updated">OID_SWITCH_NIC_UPDATED</a>

