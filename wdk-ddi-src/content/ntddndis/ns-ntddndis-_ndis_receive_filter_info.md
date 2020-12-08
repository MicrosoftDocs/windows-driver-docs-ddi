---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_INFO
title: _NDIS_RECEIVE_FILTER_INFO (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_INFO structure contains information about a receive filter that is currently configured on a miniport driver.
old-location: netvista\ndis_receive_filter_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_RECEIVE_FILTER_INFO structure"]
ms.keywords: "*PNDIS_RECEIVE_FILTER_INFO, NDIS_RECEIVE_FILTER_INFO, NDIS_RECEIVE_FILTER_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_INFO, PNDIS_RECEIVE_FILTER_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_INFO, netvista.ndis_receive_filter_info, ntddndis/NDIS_RECEIVE_FILTER_INFO, ntddndis/PNDIS_RECEIVE_FILTER_INFO, virtual_machine_queue_ref_4c711292-ce17-4eb9-a051-c32f8ad6f49e.xml"
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
req.typenames: NDIS_RECEIVE_FILTER_INFO, *PNDIS_RECEIVE_FILTER_INFO
f1_keywords:
 - _NDIS_RECEIVE_FILTER_INFO
 - ntddndis/_NDIS_RECEIVE_FILTER_INFO
 - PNDIS_RECEIVE_FILTER_INFO
 - ntddndis/PNDIS_RECEIVE_FILTER_INFO
 - NDIS_RECEIVE_FILTER_INFO
 - ntddndis/NDIS_RECEIVE_FILTER_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RECEIVE_FILTER_INFO
---

# _NDIS_RECEIVE_FILTER_INFO structure


## -description

The <b>NDIS_RECEIVE_FILTER_INFO</b> structure contains information about a receive filter that is currently configured on a miniport driver.



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

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_INFO</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_INFO</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RECEIVE_FILTER_INFO_REVISION_1

Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_REVISION_1.

### -field Flags

A bitwise OR of flags. This member is reserved for NDIS.

### -field FilterType

The type of the receive filter.

### -field FilterId

A receive filter identifier. The filter identifier
     is an integer from one up to and including the number of receive filters that the network adapter
     supports. A value of zero is not valid.

## -remarks

The <b>NDIS_RECEIVE_FILTER_INFO</b> structure is used with the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_info_array">
    NDIS_RECEIVE_FILTER_INFO_ARRAY</a> structure for the 
    OID request of <a href="/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>. This OID request enumerates receive filters that have been configured on the miniport driver. This includes packet coalescing receive filters or the receive filters configured on a  receive queue that is used in the VMQ or SR-IOV interface.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_info_array">
   NDIS_RECEIVE_FILTER_INFO_ARRAY</a>



<a href="/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>
