---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_INFO_ARRAY
title: _NDIS_RECEIVE_FILTER_INFO_ARRAY (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_INFO_ARRAY structure specifies a list of receive filters that are currently configured on a miniport driver.
old-location: netvista\ndis_receive_filter_info_array.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_RECEIVE_FILTER_INFO_ARRAY structure"]
ms.keywords: "*PNDIS_RECEIVE_FILTER_INFO_ARRAY, NDIS_RECEIVE_FILTER_INFO_ARRAY, NDIS_RECEIVE_FILTER_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_INFO_ARRAY, PNDIS_RECEIVE_FILTER_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_INFO_ARRAY, netvista.ndis_receive_filter_info_array, ntddndis/NDIS_RECEIVE_FILTER_INFO_ARRAY, ntddndis/PNDIS_RECEIVE_FILTER_INFO_ARRAY, virtual_machine_queue_ref_f87d474d-4909-48ed-8891-7213bd4dcbc1.xml"
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
req.typenames: NDIS_RECEIVE_FILTER_INFO_ARRAY, *PNDIS_RECEIVE_FILTER_INFO_ARRAY
f1_keywords:
 - _NDIS_RECEIVE_FILTER_INFO_ARRAY
 - ntddndis/_NDIS_RECEIVE_FILTER_INFO_ARRAY
 - PNDIS_RECEIVE_FILTER_INFO_ARRAY
 - ntddndis/PNDIS_RECEIVE_FILTER_INFO_ARRAY
 - NDIS_RECEIVE_FILTER_INFO_ARRAY
 - ntddndis/NDIS_RECEIVE_FILTER_INFO_ARRAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - _NDIS_RECEIVE_FILTER_INFO_ARRAY
 - PNDIS_RECEIVE_FILTER_INFO_ARRAY
 - NDIS_RECEIVE_FILTER_INFO_ARRAY
---

# _NDIS_RECEIVE_FILTER_INFO_ARRAY structure


## -description

The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure specifies a list of receive filters that are currently configured on a miniport driver.



NDIS receive filters are used in the following NDIS interfaces:
<ul>
<li>

<a href="/windows-hardware/drivers/network/ndis-packet-coalescing">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="/windows-hardware/drivers/network/managing-packet-coalescing-receive-filters">Managing Packet Coalescing Receive Filters</a>.

</li>
<li>

<a href="/windows-hardware/drivers/network/single-root-i-o-virtualization--sr-iov-">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="/windows-hardware/drivers/network/setting-a-receive-filter-on-a-virtual-port">Setting a Receive Filter on a Virtual Port</a>.

</li>
<li>

<a href="/windows-hardware/drivers/network/virtual-machine-queue--vmq-">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="/windows-hardware/drivers/network/setting-and-clearing-vmq-filters">Setting and Clearing VMQ Filters</a>.

</li>
</ul>

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_2

Added members for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_2.



#### NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_1.

### -field QueueId

A receive queue identifier. This identifier is an
     integer between zero and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Miniport drivers that support <a href="/windows-hardware/drivers/network/ndis-packet-coalescing">NDIS packet coalescing</a> or SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field FirstElementOffset

The offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_info">NDIS_RECEIVE_FILTER_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

The number of elements in the array.

### -field ElementSize

The size, in bytes, of each element in the array.

### -field Flags

A  bitwise OR of the following flags: 





#### NDIS_RECEIVE_FILTER_INFO_ARRAY_VPORT_ID_SPECIFIED

If this flag is set, information is requested about receive filters that are configured on the virtual port (VPort) specified by the <b>VPortId</b> member.

<div class="alert"><b>Note</b>  This flag is only valid for the SR-IOV interface.</div>
<div> </div>

### -field VPortId

The virtual port (VPort) identifier on which receive filters are being queried. The VPort identifier must be one of the following values:

<ul>
<li>


The identifier of a VPort that was previously allocated through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>.



</li>
<li>
A value of NDIS_DEFAULT_VPORT_ID that specifies the default VPort on the NIC switch.



</li>
</ul>
A NIC switch is supported by network adapters for the SR-IOV interface. The NIC switch can be configured to have one or more VPorts.

<div class="alert"><b>Note</b>  The <b>VPortId</b> member is only valid if the NDIS_RECEIVE_FILTER_INFO_ARRAY_VPORT_ID_SPECIFIED flag is set in <b>Flags</b>. 
</div>
<div> </div>

## -remarks

The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure is used in the 
    OID request of <a href="/windows-hardware/drivers/network/oid-receive-filter-enum-filters">
    OID_RECEIVE_FILTER_ENUM_FILTERS</a>. This OID request enumerates the receive filters on a VMQ  or SR-IOV receive queue. Each
    element in the array that follows the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure is an 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_info">
    NDIS_RECEIVE_FILTER_INFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_info">NDIS_RECEIVE_FILTER_INFO</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>

