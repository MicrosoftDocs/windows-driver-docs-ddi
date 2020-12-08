---
UID: NS:ntddndis._NDIS_NIC_SWITCH_CAPABILITIES
title: _NDIS_NIC_SWITCH_CAPABILITIES (ntddndis.h)
description: The NDIS_NIC_SWITCH_CAPABILITIES structure specifies the capabilities of a NIC switch on the network adapter.
old-location: netvista\ndis_nic_switch_capabilities.htm
tech.root: netvista
ms.date: 05/16/2019
keywords: ["NDIS_NIC_SWITCH_CAPABILITIES structure"]
ms.keywords: "*PNDIS_NIC_SWITCH_CAPABILITIES, NDIS_NIC_SWITCH_CAPABILITIES, NDIS_NIC_SWITCH_CAPABILITIES structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_CAPABILITIES, PNDIS_NIC_SWITCH_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_CAPABILITIES, netvista.ndis_nic_switch_capabilities, ntddndis/NDIS_NIC_SWITCH_CAPABILITIES, ntddndis/PNDIS_NIC_SWITCH_CAPABILITIES, virtual_machine_queue_ref_b71fb086-5613-4ebb-ac19-97bd3bd9c55f.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.typenames: NDIS_NIC_SWITCH_CAPABILITIES, *PNDIS_NIC_SWITCH_CAPABILITIES
f1_keywords:
 - _NDIS_NIC_SWITCH_CAPABILITIES
 - ntddndis/_NDIS_NIC_SWITCH_CAPABILITIES
 - PNDIS_NIC_SWITCH_CAPABILITIES
 - ntddndis/PNDIS_NIC_SWITCH_CAPABILITIES
 - NDIS_NIC_SWITCH_CAPABILITIES
 - ntddndis/NDIS_NIC_SWITCH_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_NIC_SWITCH_CAPABILITIES
---

# _NDIS_NIC_SWITCH_CAPABILITIES structure


## -description

The <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure specifies the capabilities of a NIC switch on the network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to one of the following values: 





#### NDIS_NIC_SWITCH_CAPABILITIES_REVISION_3

Added the RSS interface members for NDIS 6.60.<div class="alert"><b>Note</b>  Revision 3 of this structure is  supported only on Windows Server 2016  and later versions of Windows Server.</div>
<div> </div>


Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_CAPABILITIES_REVISION_3.



#### NDIS_NIC_SWITCH_CAPABILITIES_REVISION_2

Added the single root I/O virtualization (SR-IOV) interface members for NDIS 6.30.<div class="alert"><b>Note</b>  Revision 2 of this structure is  supported only on Windows Server 2012 and later versions of Windows Server.</div>
<div> </div>


Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_CAPABILITIES_REVISION_2.



#### NDIS_NIC_SWITCH_CAPABILITIES_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_CAPABILITIES_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.

### -field NdisReserved1

Reserved for NDIS.

### -field NumTotalMacAddresses

A ULONG value that contains the total number of media access control (MAC) addresses that the network adapter supports.

<div class="alert"><b>Note</b>  Drivers must set this member to zero for revision 2 and later revisions of this structure.</div>
<div> </div>

### -field NumMacAddressesPerPort

A ULONG value that contains the number of MAC addresses that are supported for each port.

<div class="alert"><b>Note</b>  Drivers must set this member to zero for revision 2 and later revisions of this structure.</div>
<div> </div>

### -field NumVlansPerPort

A ULONG value that contains the number of VLANs that are supported for each port.

<div class="alert"><b>Note</b>  Drivers must set this member to zero for revision 2 and later revisions of this structure.</div>
<div> </div>

### -field NdisReserved2

Reserved for NDIS.

### -field NdisReserved3

Reserved for NDIS.

### -field NicSwitchCapabilities

A ULONG value that contains a bitwise OR of the following flags that specify the capabilities of the NIC switch: 

#### NDIS_NIC_SWITCH_CAPS_RSS_ON_PF_VPORTS_SUPPORTED                        

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later. It was introduced in NDIS 6.60. </div>

Specifies that the NIC supports VMMQ for PF VPorts.

#### NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_INDIRECTION_TABLE_SUPPORTED      

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later. It was introduced in NDIS 6.60. </div>

If set to **1**, specifies that the NIC is able to maintain per-PF VPort indirection tables.

#### NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_HASH_FUNCTION_SUPPORTED          

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later. It was introduced in NDIS 6.60. </div>

If set to **1**, specifies that the NIC supports setting a different hash function per PF VPort. If this flag is set, **NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_HASH_KEY_SUPPORTED** must be set as well.

#### NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_HASH_TYPE_SUPPORTED              

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later. It was introduced in NDIS 6.60. </div>

If set to **1**, specifies that the NIC supports setting different hash types per PF VPort.

#### NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_HASH_KEY_SUPPORTED               

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later. It was introduced in NDIS 6.60. </div>

If set to **1**, specifies that the NIC supports setting a different hash secret key per PF VPort. This flag must be set if **NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_HASH_FUNCTION_SUPPORTED** is set.

#### NDIS_NIC_SWITCH_CAPS_RSS_PER_PF_VPORT_INDIRECTION_TABLE_SIZE_RESTRICTED

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later. It was introduced in NDIS 6.60. </div>

If set to **1**, specifies that the NIC has a limitation on indirection table size for PF VPorts. This flag forces the issuer of an RSS OID to use a per-PF VPort indirection table size equal to the number of VPort queues rounded up to the next power of two. This only applies to PF VPorts and does not apply to VF VPorts. This flag can be combined with the **NDIS_NIC_SWITCH_CAPS_ASYMMETRIC_QUEUE_PAIRS_FOR_NONDEFAULT_VPORT_SUPPORTED** flag (different PF VPorts can have different numbers of queues). This flag prevents VMMQ users from performing fine-grained queue steering.

#### NDIS_NIC_SWITCH_CAPS_NIC_SWITCH_WITHOUT_IOV_SUPPORTED

<div class="alert"><b>Note</b> This flag is supported in Windows Server 2016 and later.</div>

This flag, introduced with NDIS 6.60, specifies that a NIC switch can be created without the use of SR-IOV. This flag allows for separating a NIC switch from the \*SRIOV keyword, meaning that a NIC switch can be created via [OID_NIC_SWITCH_CREATE_SWITCH](/windows-hardware/drivers/network/oid-nic-switch-create-switch) even if \*SRIOV = 0.

For more information about reporting NIC switch capabilities for NDIS 6.60 and later miniport drivers, see [Determining NIC Switch Capabilities](/windows-hardware/drivers/network/determining-nic-switch-capabilities).

#### NDIS_NIC_SWITCH_CAPS_VLAN_SUPPORTED

This flag specifies that the NIC switch supports hardware packet filtering based on the virtual local area network (VLAN) identifier (ID). 

<div class="alert"><b>Note</b>  This flag should be set only if the NIC switch supports VLAN ID filtering on individual SR-IOV virtual ports (VPorts).</div>
<div> </div>


#### NDIS_NIC_SWITCH_CAPS_PER_VPORT_INTERRUPT_MODERATION_SUPPORTED

This flag specifies that the NIC switch can support interrupt moderation configuration on individual VPorts. 

#### NDIS_NIC_SWITCH_CAPS_ASYMMETRIC_QUEUE_PAIRS_FOR_NONDEFAULT_VPORT_SUPPORTED

This flag specifies that the NIC switch can configure a different number of queue pairs for each nondefault VPort. This means that each nondefault VPort can be configured asymmetrically to have a different number of queue pairs. 

If this flag is not set, all nondefault VPorts must be configured symmetrically to have the same number of queue pairs. 

Regardless of whether this flag is set, the NIC switch must support the ability to set the number of queue pairs on the default VPort. These may differ from the number of queue-pairs that are set on the nondefault VPorts.

<div class="alert"><b>Note</b>  A queue pair consists of a transmit queue and receive queue. Queue pairs associated with the default VPort are configured at the time of switch creation through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-switch">OID_NIC_SWITCH_CREATE_SWITCH</a>.
One or more queue pairs are configured on a nondefault VPort through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>.
</div>
<div> </div>
For more information, see <a href="/windows-hardware/drivers/network/symmetric-and-asymmetric-assignment-of-queue-pairs">Symmetric and Asymmetric Assignment of Queue Pairs</a>.





#### NDIS_NIC_SWITCH_CAPS_VF_RSS_SUPPORTED

This flag specifies that queue pairs from nondefault VPorts that are attached to a PCI Express (PCIe) Virtual Function (VF) can be used for receive side scaling (RSS). The VF miniport driver runs in the guest operating system of a Hyper-V child partition. 

If this flag is set, the miniport driver supports RSS on a VF and can use  one or more of the queue pairs from the nondefault VPort for RSS.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, only one nondefault VPort can be attached to a VF.</div>
<div> </div>


#### NDIS_NIC_SWITCH_CAPS_SINGLE_VPORT_POOL

This flag specifies that the nondefault VPorts can be created in a non-reserved manner from the VPort pool on the network adapter. This allows available nondefault VPorts to be created and assigned on an as-needed basis to the PF and allocated VFs. If the network adapter supports the virtual machine queue (VMQ) interface, nondefault VPorts that are assigned to the PF can also be used for VM receive queues.

<div class="alert"><b>Note</b>  The default VPort is always reserved for assignment to the PF.</div>
<div> </div>
If this flag is set, available nondefault VPorts are created and assigned to the PF and allocated VFs. However, this mechanism does not reserve nondefault VPorts for VF creation and assignment. As a result, situations may occur where a VF may not be assigned a VPort if the pool has been exhausted of available VPorts.

<div class="alert"><b>Note</b>  If a VF cannot be assigned a VPort, packet traffic over the VF occurs over the SR-IOV synthetic data path. For more information about this data path, see <a href="/windows-hardware/drivers/network/sr-iov-data-paths">SR-IOV Data Paths</a>.</div>
<div> </div>
If this flag is not set, the creation and assignment of nondefault VPorts is reserved for VF assignment.  Additional nondefault VPorts  can be created and assigned to the PF. 

For more information about VMQ, see <a href="/windows-hardware/drivers/network/virtual-machine-queue--vmq-">Virtual Machine Queue (VMQ)</a>.

For more information about VPorts, see <a href="/windows-hardware/drivers/network/managing-virtual-ports">Managing Virtual Ports</a>.

### -field MaxNumSwitches

A ULONG value that specifies the maximum number of switches that can be created on the network adapter's PCI Express (PCIe) Physical Function (PF).

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, Windows only supports the default NIC switch on the network adapter. Therefore, this member must always be set to one. 
</div>
<div> </div>

### -field MaxNumVPorts

A ULONG value that specifies the maximum number of VPorts that can be created on a network adapter. This includes the default VPort that is always attached to the PF. 

<div class="alert"><b>Note</b>  The NIC switch must support at least (<b>MaxNumVFs</b> + 1) VPorts.</div>
<div> </div>

### -field NdisReserved4

Reserved for NDIS.

### -field MaxNumVFs

A ULONG value that specifies the maximum number of VFs that can be created on the NIC switch. 

<div class="alert"><b>Note</b>  Depending on the available hardware resources on the network adapter, the miniport driver can set the <b>MaxNumVFs</b> member to a value that is less than its <b>*NumVFs</b>
keyword. For more information about this keyword, see <a href="/windows-hardware/drivers/network/standardized-inf-keywords-for-sr-iov">Standardized INF Keywords for SR-IOV</a>.</div>
<div> </div>

### -field MaxNumQueuePairs

A ULONG value that specifies the maximum number of queue pairs that can be assigned to all VPorts. This includes the default VPort that is attached to the PF.

<div class="alert"><b>Note</b>  This value must be greater than or equal to the value of <b>MaxNumVPorts</b>.</div>
<div> </div>

### -field NdisReserved5

Reserved for NDIS.

### -field NdisReserved6

Reserved for NDIS.

### -field NdisReserved7

Reserved for NDIS.

### -field MaxNumQueuePairsPerNonDefaultVPort

A ULONG value that specifies the maximum number of queue pairs that can be assigned to a nondefault VPort. 

This value is specified in powers of 2, and provides for asymmetric configuration and assignment of queue pairs to VPorts. For more information, see <a href="/windows-hardware/drivers/network/symmetric-and-asymmetric-assignment-of-queue-pairs">Symmetric and Asymmetric Assignment of Queue Pairs</a>.

### -field NdisReserved8

Reserved for NDIS.

### -field NdisReserved9

Reserved for NDIS.

### -field NdisReserved10

Reserved for NDIS.

### -field NdisReserved11

Reserved for NDIS.

### -field NdisReserved12

Reserved for NDIS.

### -field MaxNumMacAddresses

A ULONG value that specifies the maximum number of unicast MAC address filters that are available on the NIC switch.  

<div class="alert"><b>Note</b>  This value must be greater than or equal to the value of <b>MaxNumVPorts</b>. This enables each VPort (including the default VPort) to be configured to have at least one unicast MAC address filter.</div>
<div> </div>

### -field NdisReserved13

Reserved for NDIS.

### -field NdisReserved14

Reserved for NDIS.

### -field NdisReserved15

Reserved for NDIS.

### -field NdisReserved16

Reserved for NDIS.

### -field NdisReserved17

Reserved for NDIS.

### -field MaxNumRssCapableNonDefaultPFVPorts

A ULONG value that specifies the maximum number of RSS-capable non-default PFVPorts.

### -field NumberOfIndirectionTableEntriesForDefaultVPort

A ULONG value that specifies the number of indirection table entries for the default VPort.

### -field NumberOfIndirectionTableEntriesPerNonDefaultPFVPort

A ULONG value that specifies the number of indirection table entries for each non-default PFVPort.

### -field MaxNumQueuePairsForDefaultVPort

A ULONG value that specifies the maximum number of queue pairs that can be assigned to the default VPort. 

This value is specified in powers of 2, and provides for asymmetric configuration and assignment of queue pairs to VPorts. For more information, see <a href="/windows-hardware/drivers/network/symmetric-and-asymmetric-assignment-of-queue-pairs">Symmetric and Asymmetric Assignment of Queue Pairs</a>.

## -remarks

    The <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure is used in the 
    members of the following structures:

<ul>
<li>
The <b>HardwareNicSwitchCapabilities</b> and 
    <b>CurrentNicSwitchCapabilities</b> members of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">
    NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure.

</li>
<li>
The 
    <b>NicSwitchCapabilities</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">
    NDIS_FILTER_ATTACH_PARAMETERS</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structures. 

</li>
</ul>
OID query requests of <a href="/windows-hardware/drivers/network/oid-nic-switch-current-capabilities">
    OID_NIC_SWITCH_CURRENT_CAPABILITIES</a> and 
    <a href="/windows-hardware/drivers/network/oid-nic-switch-hardware-capabilities">
    OID_NIC_SWITCH_HARDWARE_CAPABILITIES</a> return an <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-current-capabilities">OID_NIC_SWITCH_CURRENT_CAPABILITIES</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-hardware-capabilities">OID_NIC_SWITCH_HARDWARE_CAPABILITIES</a>
