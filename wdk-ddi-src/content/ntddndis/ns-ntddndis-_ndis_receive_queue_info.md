---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_INFO
title: _NDIS_RECEIVE_QUEUE_INFO (ntddndis.h)
description: The NDIS_RECEIVE_QUEUE_INFO structure contains information about a receive queue on a network adapter.
old-location: netvista\ndis_receive_queue_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_RECEIVE_QUEUE_INFO structure"]
ms.keywords: "*PNDIS_RECEIVE_QUEUE_INFO, NDIS_RECEIVE_QUEUE_INFO, NDIS_RECEIVE_QUEUE_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_INFO, PNDIS_RECEIVE_QUEUE_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_INFO, netvista.ndis_receive_queue_info, ntddndis/NDIS_RECEIVE_QUEUE_INFO, ntddndis/PNDIS_RECEIVE_QUEUE_INFO, virtual_machine_queue_ref_5052da2e-c93a-40f9-b129-07538556ef29.xml"
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
req.typenames: NDIS_RECEIVE_QUEUE_INFO, *PNDIS_RECEIVE_QUEUE_INFO
f1_keywords:
 - _NDIS_RECEIVE_QUEUE_INFO
 - ntddndis/_NDIS_RECEIVE_QUEUE_INFO
 - PNDIS_RECEIVE_QUEUE_INFO
 - ntddndis/PNDIS_RECEIVE_QUEUE_INFO
 - NDIS_RECEIVE_QUEUE_INFO
 - ntddndis/NDIS_RECEIVE_QUEUE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RECEIVE_QUEUE_INFO
---

# _NDIS_RECEIVE_QUEUE_INFO structure


## -description

The <b>NDIS_RECEIVE_QUEUE_INFO</b> structure contains information about a receive queue on a network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_RECEIVE_QUEUE_INFO</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_RECEIVE_QUEUE_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to one of the following values: 





#### NDIS_RECEIVE_QUEUE_INFO_REVISION_2

Added additional members for NDIS 6.30.

<div class="alert"><b>Note</b>  Revision 2 of this structure is  supported only on Windows Server 2012 and later versions of Windows Server.</div>

Set the <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_INFO_REVISION_2</b>.

#### NDIS_RECEIVE_QUEUE_INFO_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_INFO_REVISION_1</b>.

### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field QueueType

An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_receive_queue_type">NDIS_RECEIVE_QUEUE_TYPE</a> enumeration
     value that specifies the type of the receive queue.

### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a receive queue identifier. This identifier is an
     integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies
     the default receive queue.

### -field QueueGroupId

This member is reserved for NDIS.

### -field QueueState

An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_receive_queue_operational_state">
     NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a> enumeration value that specifies the operational state of the
     receive queue.

### -field ProcessorAffinity

A <b>GROUP_AFFINITY</b> bitmap that specifies the CPU that the queue has affinity with. For example,
     setting bit 0 indicates that CPU 0 is used, setting bit 1 indicates that CPU 1 is used, and so on. Because a VM queue is associated with one CPU, all receive indications for the queue are handled on that processor.

### -field NumSuggestedReceiveBuffers

A <b>ULONG</b> value that contains a suggested value for the number of receive buffers that the network adapter should use to support the queue. This number can be adjusted relative to the resources that the
     miniport driver has available or in proportion to the number that the network adapter uses for other
     queues. For example, the actual number of receive buffers could be double or half of this suggested
     value.

### -field MSIXTableEntry

A <b>ULONG</b> value that contains the MSI-X table entry index for the queue.

### -field LookaheadSize

A <b>ULONG</b> value for the size, in bytes, of the lookahead size requirement for this queue. A network adapter that supports lookahead in VM queues splits a received packet at an offset that is equal to or
     greater than the requested lookahead size and uses DMA to transfer the lookahead data and the
     post-lookahead data to separate shared memory segments.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. The value of this member must be set to zero.</div>

### -field VmName

An <b>NDIS_VM_NAME</b> value that contains the user-friendly description of the virtual machine.

### -field QueueName

An <b>NDIS_QUEUE_NAME</b> value that contains the user-friendly description of the queue.

### -field NumFilters

A ULONG value that specifies the number of receive filters that have been configured on the network adapter.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, the miniport driver must maintain a counter for the current number of receive filters that are set on the network adapter. The driver must increment the counter each time a receive filter is set through an OID set request of <a href="/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>.  The driver must also decrement the counter each time a receive filter is  cleared through an OID set request of <a href="/windows-hardware/drivers/network/oid-receive-filter-clear-filter">OID_RECEIVE_FILTER_CLEAR_FILTER</a>.</div>

### -field InterruptCoalescingDomainId

A ULONG value that is reserved for use by NDIS. This value is used for informational purposes by the miniport driver.

## -remarks

The <b>NDIS_RECEIVE_QUEUE_INFO</b> structure is used with the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info_array">
    NDIS_RECEIVE_QUEUE_INFO_ARRAY</a> structure for the 
    <a href="/windows-hardware/drivers/network/oid-receive-filter-enum-queues">
    OID_RECEIVE_FILTER_ENUM_QUEUES</a> OID that enumerates receive queues on a network adapter.

With a successful return from the <a href="/windows-hardware/drivers/network/oid-receive-filter-enum-queues">
    OID_RECEIVE_FILTER_ENUM_QUEUES</a>, NDIS provides an
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info_array">NDIS_RECEIVE_QUEUE_INFO_ARRAY</a> structure that defines the properties of the receive queue array. Each
    element in the array is an <b>NDIS_RECEIVE_QUEUE_INFO</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info_array">NDIS_RECEIVE_QUEUE_INFO_ARRAY</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_receive_queue_operational_state">
   NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_receive_queue_type">NDIS_RECEIVE_QUEUE_TYPE</a>



<a href="/windows-hardware/drivers/network/oid-receive-filter-clear-filter">OID_RECEIVE_FILTER_CLEAR_FILTER</a>



<a href="/windows-hardware/drivers/network/oid-receive-filter-enum-queues">OID_RECEIVE_FILTER_ENUM_QUEUES</a>



<a href="/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>
