---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS
title: _NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure specifies the parameters to clear a receive filter on a network adapter.
old-location: netvista\ndis_receive_filter_clear_parameters.htm
tech.root: netvista
ms.assetid: 101f9fea-cfc2-4ea5-82ee-a260d10b5a96
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, netvista.ndis_receive_filter_clear_parameters, ntddndis/NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, ntddndis/PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, virtual_machine_queue_ref_c0ec4d22-f248-4fe1-855e-99cfe6b2cd1f.xml"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, *PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS
---

# _NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure


## -description



The <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure specifies the parameters to clear a
  receive filter on a network adapter. 



NDIS receive filters are used in the following NDIS interfaces:
<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-packet-coalescing">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-packet-coalescing-receive-filters">Managing Packet Coalescing Receive Filters</a>.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/single-root-i-o-virtualization--sr-iov-">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/setting-a-receive-filter-on-a-virtual-port">Setting a Receive Filter on a Virtual Port</a>.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/virtual-machine-queue--vmq-">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/setting-and-clearing-vmq-filters">Setting and Clearing VMQ Filters</a>.

</li>
</ul>

## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_CLEAR_PARAMETERS_REVISION_1.


### -field Flags

A bitwise OR of flags. This member is reserved for NDIS.


### -field QueueId

A receive queue identifier. This identifier is an
     integer between zero and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Miniport drivers that support <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-packet-coalescing">NDIS packet coalescing</a> or the SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field FilterId

A receive filter identifier. The filter identifier
     is an integer from one to the number of receive filters that the network adapter supports. A value of zero is
     not valid.


## -remarks



The <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure is used with OID requests of   
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-clear-filter">OID_RECEIVE_FILTER_CLEAR_FILTER</a> to specify a filter to clear on a VMQ or SR-IOV VPort receive queue. The filter was
    previously set on the queue with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-set-filter">
    OID_RECEIVE_FILTER_SET_FILTER</a> OID.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-clear-filter">OID_RECEIVE_FILTER_CLEAR_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>
 

 

