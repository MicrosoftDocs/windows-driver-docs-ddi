---
UID: NS:ntddndis._NDIS_NIC_SWITCH_CAPABILITIES
title: "_NDIS_NIC_SWITCH_CAPABILITIES"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_CAPABILITIES structure specifies the capabilities of a NIC switch on the network adapter.
old-location: netvista\ndis_nic_switch_capabilities.htm
old-project: netvista
ms.assetid: bc4b56bd-583f-4b41-b5a7-90958ce65f42
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_NIC_SWITCH_CAPABILITIES, ,, A, B, C, D, E, H, I, L, N, NDIS_NIC_SWITCH_CAPABILITIES, NDIS_NIC_SWITCH_CAPABILITIES structure [Network Drivers Starting with Windows Vista], P, PNDIS_NIC_SWITCH_CAPABILITIES, PNDIS_NIC_SWITCH_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], S, T, W, _, _NDIS_NIC_SWITCH_CAPABILITIES, netvista.ndis_nic_switch_capabilities, ntddndis/NDIS_NIC_SWITCH_CAPABILITIES, ntddndis/PNDIS_NIC_SWITCH_CAPABILITIES, virtual_machine_queue_ref_b71fb086-5613-4ebb-ac19-97bd3bd9c55f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_NIC_SWITCH_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_CAPABILITIES, *PNDIS_NIC_SWITCH_CAPABILITIES
---

# _NDIS_NIC_SWITCH_CAPABILITIES structure


## -description


The <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure specifies the capabilities of a NIC switch on the network adapter.


## -syntax


````
typedef struct _NDIS_NIC_SWITCH_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              NdisReserved1;
  ULONG              NumTotalMacAddresses;
  ULONG              NumMacAddressesPerPort;
  ULONG              NumVlansPerPort;
  ULONG              NdisReserved2;
  ULONG              NdisReserved3;
#if (NDIS_SUPPORT_NDIS630)
  ULONG              NicSwitchCapabilities;
  ULONG              MaxNumSwitches;
  ULONG              MaxNumVPorts;
  ULONG              NdisReserved4;
  ULONG              MaxNumVFs;
  ULONG              MaxNumQueuePairs;
  ULONG              NdisReserved5;
  ULONG              NdisReserved6;
  ULONG              NdisReserved7;
  ULONG              MaxNumQueuePairsPerNonDefaultVPort;
  ULONG              NdisReserved8;
  ULONG              NdisReserved9;
  ULONG              NdisReserved10;
  ULONG              NdisReserved11;
  ULONG              NdisReserved12;
  ULONG              MaxNumMacAddresses;
  ULONG              NdisReserved13;
  ULONG              NdisReserved14;
  ULONG              NdisReserved15;
  ULONG              NdisReserved16;
  ULONG              NdisReserved17;
#endif 
#if (NDIS_SUPPORT_NDIS660)
  ULONG              MaxNumRssCapableNonDefaultPFVPorts;
  ULONG              NumberOfIndirectionTableEntriesForDefaultVPort;
  ULONG              NumberOfIndirectionTableEntriesPerNonDefaultPFVPort;
  ULONG              MaxNumQueuePairsForDefaultVPort;
#endif 
} NDIS_NIC_SWITCH_CAPABILITIES, *PNDIS_NIC_SWITCH_CAPABILITIES;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

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

<div class="alert"><b>Note</b>  A queue pair consists of a transmit queue and receive queue. Queue pairs associated with the default VPort are configured at the time of switch creation through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a>.
One or more queue pairs are configured on a nondefault VPort through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.
</div>
<div> </div>
For more information, see <a href="https://msdn.microsoft.com/B4BA1567-D536-4E7D-924C-7476FB82DAEB">Symmetric and Asymmetric Assignment of Queue Pairs</a>.





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

<div class="alert"><b>Note</b>  If a VF cannot be assigned a VPort, packet traffic over the VF occurs over the SR-IOV synthetic data path. For more information about this data path, see <a href="https://msdn.microsoft.com/04D85D46-DF0B-416F-95E8-F6E8B32E44A6">SR-IOV Data Paths</a>.</div>
<div> </div>
If this flag is not set, the creation and assignment of nondefault VPorts is reserved for VF assignment.  Additional nondefault VPorts  can be created and assigned to the PF. 

For more information about VMQ, see <a href="https://msdn.microsoft.com/c502c7d6-bdf1-4656-b5a5-339250910f08">Virtual Machine Queue (VMQ)</a>.

For more information about VPorts, see <a href="https://msdn.microsoft.com/BF3DFE01-6583-4FBB-AFFA-2C017A3D9A05">Managing Virtual Ports</a>.



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
keyword. For more information about this keyword, see <a href="https://msdn.microsoft.com/5CA33B4F-E43A-4EB6-BCAB-365CA1FD3EF2">Standardized INF Keywords for SR-IOV</a>.</div>
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

This value is specified in powers of 2, and provides for asymmetric configuration and assignment of queue pairs to VPorts. For more information, see <a href="https://msdn.microsoft.com/B4BA1567-D536-4E7D-924C-7476FB82DAEB">Symmetric and Asymmetric Assignment of Queue Pairs</a>.


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

This value is specified in powers of 2, and provides for asymmetric configuration and assignment of queue pairs to VPorts. For more information, see <a href="https://msdn.microsoft.com/B4BA1567-D536-4E7D-924C-7476FB82DAEB">Symmetric and Asymmetric Assignment of Queue Pairs</a>.


## -remarks




    The <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure is used in the 
    members of the following structures:

<ul>
<li>
The <b>HardwareNicSwitchCapabilities</b> and 
    <b>CurrentNicSwitchCapabilities</b> members of the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">
    NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure.

</li>
<li>
The 
    <b>NicSwitchCapabilities</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
    NDIS_FILTER_ATTACH_PARAMETERS</a> and 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structures. 

</li>
</ul>
OID query requests of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-nic-switch-current-capabilities">
    OID_NIC_SWITCH_CURRENT_CAPABILITIES</a> and 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-nic-switch-hardware-capabilities">
    OID_NIC_SWITCH_HARDWARE_CAPABILITIES</a> return an <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-nic-switch-current-capabilities">OID_NIC_SWITCH_CURRENT_CAPABILITIES</a>



<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-nic-switch-hardware-capabilities">OID_NIC_SWITCH_HARDWARE_CAPABILITIES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_CAPABILITIES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

