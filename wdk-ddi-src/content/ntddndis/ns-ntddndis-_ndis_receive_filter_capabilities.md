---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_CAPABILITIES
title: "_NDIS_RECEIVE_FILTER_CAPABILITIES"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_CAPABILITIES structure specifies the receive filtering capabilities of a network adapter.
old-location: netvista\ndis_receive_filter_capabilities.htm
old-project: netvista
ms.assetid: aecc1fe0-03f9-44be-9a38-b689eee4c5a6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_CAPABILITIES, NDIS_RECEIVE_FILTER_CAPABILITIES, NDIS_RECEIVE_FILTER_CAPABILITIES structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_CAPABILITIES, PNDIS_RECEIVE_FILTER_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_CAPABILITIES, netvista.ndis_receive_filter_capabilities, ntddndis/NDIS_RECEIVE_FILTER_CAPABILITIES, ntddndis/PNDIS_RECEIVE_FILTER_CAPABILITIES, virtual_machine_queue_ref_51c84771-6803-4059-9011-df2d870614a0.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_FILTER_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_CAPABILITIES, *PNDIS_RECEIVE_FILTER_CAPABILITIES
---

# _NDIS_RECEIVE_FILTER_CAPABILITIES structure


## -description


The <b>NDIS_RECEIVE_FILTER_CAPABILITIES</b> structure specifies the  receive filtering capabilities of a
  network adapter.

NDIS receive filters are used in the following NDIS interfaces:
<ul>
<li>

<a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/20EA71E0-B880-4891-A12E-76F4C9AB16E6">Managing Packet Coalescing Receive Filters</a>.

</li>
<li>

<a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/F0137D59-1701-4DFC-BB30-27E477FC0706">Setting a Receive Filter on a Virtual Port</a>.

</li>
<li>

<a href="https://msdn.microsoft.com/c502c7d6-bdf1-4656-b5a5-339250910f08">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/bfee8a3c-d2be-4718-beb4-067b66756a41">Setting and Clearing VMQ Filters</a>.

</li>
</ul>

## -syntax


````
typedef struct _NDIS_RECEIVE_FILTER_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              EnabledFilterTypes;
  ULONG              EnabledQueueTypes;
  ULONG              NumQueues;
  ULONG              SupportedQueueProperties;
  ULONG              SupportedFilterTests;
  ULONG              SupportedHeaders;
  ULONG              SupportedMacHeaderFields;
  ULONG              MaxMacHeaderFilters;
  ULONG              MaxQueueGroups;
  ULONG              MaxQueuesPerQueueGroup;
  ULONG              MinLookaheadSplitSize;
  ULONG              MaxLookaheadSplitSize;
#if NDIS_SUPPORT_NDIS630
  ULONG              SupportedARPHeaderFields;
  ULONG              SupportedIPv4HeaderFields;
  ULONG              SupportedIPv6HeaderFields;
  ULONG              SupportedUdpHeaderFields;
  ULONG              MaxFieldTestsPerPacketCoalescingFilter;
  ULONG              MaxPacketCoalescingFilters;
  ULONG              NdisReserved;
#endif 
} NDIS_RECEIVE_FILTER_CAPABILITIES, *PNDIS_RECEIVE_FILTER_CAPABILITIES;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_CAPABILITIES</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_CAPABILITIES</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RECEIVE_FILTER_CAPABILITIES_REVISION_2

Added  
        various members for NDIS 6.30 and later.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_CAPABILITIES_REVISION_2.



#### NDIS_RECEIVE_FILTER_CAPABILITIES_REVISION_1

Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_CAPABILITIES_REVISION_1.


### -field Flags

A bitwise OR of flags. This member is reserved for NDIS.


### -field EnabledFilterTypes

A bitwise OR of flags that specify the types of receive filters that are enabled. The
     following filter type flag is valid.
     





#### NDIS_RECEIVE_FILTER_VMQ_FILTERS_ENABLED

Specifies that VMQ filters are enabled.

<div class="alert"><b>Note</b>  The miniport driver should set this flag if the miniport driver is enabled to use the SR-IOV interface.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_PACKET_COALESCING_FILTERS_ENABLED

Specifies that NDIS packet coalescing receive filters are enabled.


### -field EnabledQueueTypes

A bitwise OR of flags that specify the types of receive queues that are enabled. The
     following queue type flag is valid.
     





#### NDIS_RECEIVE_FILTER_VM_QUEUES_ENABLED

Specifies that virtual machine (VM) queues are enabled.  VM queues are used when the miniport driver is enabled to use the VMQ interface.

<div class="alert"><b>Note</b>  The miniport driver must not set this flag if the miniport driver is enabled to only use the SR-IOV interface. For more information on how these interfaces are enabled, see <a href="https://msdn.microsoft.com/EF556563-4097-4388-A563-29FC891AC626">Handling SR-IOV, VMQ, and RSS Standardized INF Keywords</a>.</div>
<div> </div>

### -field NumQueues

The number of VM queues that the network adapter supports.

<div class="alert"><b>Note</b>  If the miniport driver is enabled to use the SR-IOV interface, it must set this member to zero. When use of the SR-IOV interface is enabled, NDIS uses virtual ports (VPorts) for receive and transmit queues instead of VM queues.
</div>
<div> </div>

### -field SupportedQueueProperties

A bitwise OR of flags that specify the VM queue properties that the network adapter supports. The
     following flags are defined:
     





#### NDIS_RECEIVE_FILTER_MSI_X_SUPPORTED

The network adapter uses MSI-X for receive queue interrupt generation. This flag is mandatory for miniport drivers that support the VMQ or SR-IOV interface.



#### NDIS_RECEIVE_FILTER_VM_QUEUE_SUPPORTED

The network adapter provides the minimum requirements to support VM  queue packet filtering. 

The miniport driver must set this flag if it is enabled to use the VMQ or SR-IOV interface.

For more information about VMQ requirements for VM queue packet filtering, see <a href="https://msdn.microsoft.com/bfee8a3c-d2be-4718-beb4-067b66756a41">Setting and Clearing VMQ Filters</a>.



For more information about SR-IOV requirements for VM queue packet filtering, see <a href="https://msdn.microsoft.com/F0137D59-1701-4DFC-BB30-27E477FC0706">Setting a Receive Filter on a Virtual Port</a>.





#### NDIS_RECEIVE_FILTER_LOOKAHEAD_SPLIT_SUPPORTED

The network adapter supports VM queues that split an incoming received packet at the lookahead
       offset. This offset is equal to or greater than the requested lookahead size. The network adapter uses DMA to transfer the lookahead
       and post-lookahead data to separate shared memory segments.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. Miniport drivers that support this version of NDIS must not set this flag.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_DYNAMIC_PROCESSOR_AFFINITY_CHANGE_SUPPORTED

The  network adapter supports the ability to dynamically change one of the following processor affinity attributes:

<ul>
<li>
The processor affinity of a VM queue in the VMQ interface. The processor affinity is changed through an OID set request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-parameters">OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a>.

</li>
<li>
The processor affinity of a nondefault virtual port (VPort), which was created in the SR-IOV interface and is attached to the PCI Express (PCIe) physical function (PF) of the network adapter. The processor affinity is changed through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>.

</li>
</ul>
<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later. Miniport drivers that support the VMQ or SR-IOV interface must set this flag.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_INTERRUPT_VECTOR_COALESCING_SUPPORTED

The network adapter supports interrupt coalescing for received packets on any of the following: 

<ul>
<li>
Multiple VM queues in the VMQ interface.

</li>
<li>
Multiple VPorts that are attached to the PF in the SR-IOV interface.

</li>
</ul>
If this flag is set, the network adapter must coalesce receive interrupts for VM queues or VPorts that have the same processor affinity.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later. Miniport drivers that support the VMQ or SR-IOV interface must set this flag.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_IMPLAT_MIN_OF_QUEUES_MODE

Indicates that the number of VM queues available  is the minimum number of queues available from any member of a Load Balancing Failover (LBFO) team. This flag applies to LBFO filters only. This flag is not set for miniports.



#### NDIS_RECEIVE_FILTER_IMPLAT_SUM_OF_QUEUES_MODE

Indicates that the number of VM queues available is the sum of all the queues available from every member of an LBFO team. This flag applies to LBFO filters only. This flag is not set for miniports.



#### NDIS_RECEIVE_FILTER_PACKET_COALESCING_SUPPORTED_ON_DEFAULT_QUEUE

The network adapter supports NDIS packet coalescing. Packet coalescing is only supported on the default receive queue of the network adapter. This receive queue has an identifier of NDIS_DEFAULT_RECEIVE_QUEUE_ID.


<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>

### -field SupportedFilterTests

A bitwise OR of flags that specify the test operations that a miniport
     driver supports. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_TEST_HEADER_FIELD_EQUAL_SUPPORTED

The network adapter supports testing the selected header field to determine whether it is equal to a
       given value.

<div class="alert"><b>Note</b>  If the miniport driver supports the VMQ or SR-IOV interfaces, it must set this flag.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_TEST_HEADER_FIELD_MASK_EQUAL_SUPPORTED

The network adapter supports masking (that is, a bitwise AND) of the selected header field to
       determine whether the result is equal to a specified value.



#### NDIS_RECEIVE_FILTER_TEST_HEADER_FIELD_NOT_EQUAL_SUPPORTED

The network adapter supports testing the selected header field to determine whether it is not equal to a
       specified value.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>

### -field SupportedHeaders

A bitwise OR of flags that specify the types of network packet headers that
     a miniport driver can inspect. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_MAC_HEADER_SUPPORTED

The network adapter can inspect the media access control (MAC) header of a network packet. The <b>SupportedMacHeaderFields</b> member defines the various fields from the MAC header that can be inspected.



#### NDIS_RECEIVE_FILTER_ARP_HEADER_SUPPORTED

The network adapter can inspect the Address Resolution Protocol (ARP) header of a network packet. The <b>SupportedArpHeaderFields</b> member defines the various fields from the ARP header that can be inspected.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_IPV4_HEADER_SUPPORTED

The network adapter can inspect the IP version 4 (IPv4) header of a network packet. The <b>SupportedIPv4HeaderFields</b> member defines the various fields from the IPv4 header that can be inspected.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_IPV6_HEADER_SUPPORTED

The network adapter can inspect the IP version 6 (IPv6) header of a network packet. The <b>SupportedIPv6HeaderFields</b> member defines the various fields from the IPv6 header that can be inspected.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_UDP_HEADER_SUPPORTED

The network adapter can inspect the User Datagram Protocol
(UDP) header of a network packet. The <b>SupportedIPv6HeaderFields</b> member defines the various fields from the UDP header that can be inspected.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>

### -field SupportedMacHeaderFields

A bitwise OR of flags that specify the types of MAC header fields that a
     miniport driver can inspect. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_MAC_HEADER_DEST_ADDR_SUPPORTED

The network adapter supports inspecting and filtering that are based on the destination MAC
       address in the MAC header.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, miniport drivers that support the VMQ or SR-IOV interface must set this flag.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_MAC_HEADER_SOURCE_ADDR_SUPPORTED

The network adapter supports inspecting and filtering that are based on the source MAC address
       in the MAC header.



#### NDIS_RECEIVE_FILTER_MAC_HEADER_PROTOCOL_SUPPORTED

The network adapter supports inspecting and filtering that are based on the EtherType identifier
       in the MAC header. For example, the EtherType identifier for IPv4 packets is 0x0800.



#### NDIS_RECEIVE_FILTER_MAC_HEADER_VLAN_ID_SUPPORTED

The network adapter supports inspecting and filtering that are based on the VLAN identifier in
       the MAC header.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, this flag is optional. If the miniport driver does not set this flag, the network adapter should inspect and filter the specified MAC address fields. If a VLAN tag is present in the received packet, the network adapter must remove it from the packet data. The miniport driver must   put the VLAN tag in an <a href="..\ndis\ns-ndis-_ndis_net_buffer_list_8021q_info.md">NDIS_NET_BUFFER_LIST_8021Q_INFO</a> structure that is associated with the packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_MAC_HEADER_PRIORITY_SUPPORTED

The network adapter supports inspecting and filtering that are based on the priority tag in the
       MAC header.



#### NDIS_RECEIVE_FILTER_MAC_HEADER_PACKET_TYPE_SUPPORTED

The network adapter supports inspecting and filtering that are based on the packet type field of the IEEE 802.2 subnetwork access protocol (SNAP) header in an 802.3 MAC header.

<div class="alert"><b>Note</b>  This flag is supported in NDIS 6.30 and later.</div>
<div> </div>

### -field MaxMacHeaderFilters

The maximum number of MAC header filters that the miniport driver
     supports.


### -field MaxQueueGroups

This member is reserved for NDIS.


### -field MaxQueuesPerQueueGroup

This member is reserved for NDIS.


### -field MinLookaheadSplitSize

The minimum size, in bytes, that the network adapter supports for lookahead
     packet buffers.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. Miniport drivers that support this version of NDIS must set this member to zero.</div>
<div> </div>

### -field MaxLookaheadSplitSize

The maximum size, in bytes, that the network adapter supports for lookahead
     packet buffers.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. Miniport drivers that support this version of NDIS must set this member to zero.</div>
<div> </div>

### -field SupportedARPHeaderFields

A bitwise OR of flags that specify the types of ARP header fields that a
     miniport driver can inspect. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_ARP_HEADER_OPERATION_SUPPORTED

The network adapter supports receive filtering on the ARP operation field.



#### NDIS_RECEIVE_FILTER_ARP_HEADER_SPA_SUPPORTED

The network adapter supports receive filtering on the ARP source protocol address (SPA) field.



#### NDIS_RECEIVE_FILTER_ARP_HEADER_TPA_SUPPORTED

The network adapter supports receive filtering on the ARP target protocol address (TPA) field.


### -field SupportedIPv4HeaderFields

A bitwise OR of flags that specify the types of IPv4 header fields that a
     miniport driver can inspect. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_IPV4_HEADER_PROTOCOL_SUPPORTED

The network adapter supports receive filtering on the IPv4 protocol field.


### -field SupportedIPv6HeaderFields

A bitwise OR of flags that specify the types of IPv6 header fields that a
     miniport driver can inspect. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_IPV6_HEADER_PROTOCOL_SUPPORTED

The network adapter supports receive filtering on the IPv6 protocol field.


### -field SupportedUdpHeaderFields

A bitwise OR of flags that specify the types of IPv6 header fields that a
     miniport driver can inspect. The following flags are defined:
     





#### NDIS_RECEIVE_FILTER_UDP_HEADER_DEST_PORT_SUPPORTED

The network adapter supports receive filtering on the UDP destination port field.

<div class="alert"><b>Note</b>  If the received UDP packet contains IPv4  options or IPv6 extension headers, the network adapter can automatically drop the  received packet and treat it as if it failed the UDP filter test.</div>
<div> </div>

### -field MaxFieldTestsPerPacketCoalescingFilter

The maximum number of tests on packet header fields that can be specified for a single packet coalescing filter. For more information about packet coalescing, see <a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS Packet Coalescing</a>.

<div class="alert"><b>Note</b>  Network adapters that support packet coalescing must support five or more packet header fields that can be specified for a single packet coalescing filter. If the adapter does not support packet coalescing, the miniport driver must set this value to zero.</div>
<div> </div>

### -field MaxPacketCoalescingFilters

The maximum number of packet coalescing receive filters that are supported by the network adapter.

<div class="alert"><b>Note</b>  Network adapters that support packet coalescing must support ten or more packet coalescing filters. If the adapter does not support packet coalescing, the miniport driver must set this value to zero.</div>
<div> </div>

### -field NdisReserved

Reserved. Set to 0.


## -remarks



The <b>NDIS_RECEIVE_FILTER_CAPABILITIES</b> structure is used in the 
    <b>ReceiveFilterCapabilities</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">
    NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>, 
    <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
    NDIS_FILTER_ATTACH_PARAMETERS</a>, and 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structures and the
    return result of the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-hardware-capabilities">
    OID_RECEIVE_FILTER_HARDWARE_CAPABILITIES</a> OID query.

Many of the members and flag settings of the <b>NDIS_RECEIVE_FILTER_CAPABILITIES</b> structure are valid only if the miniport driver is enabled to use the VMQ or SR-IOV interface. The miniport driver is enabled to use these interfaces through standardized INF keywords. For more information, see <a href="https://msdn.microsoft.com/EF556563-4097-4388-A563-29FC891AC626">Handling SR-IOV, VMQ, and RSS Standardized INF Keywords</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_parameters.md">NDIS_RECEIVE_QUEUE_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_info.md">NDIS_RECEIVE_QUEUE_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-hardware-capabilities">
   OID_RECEIVE_FILTER_HARDWARE_CAPABILITIES</a>



<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_CAPABILITIES structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

