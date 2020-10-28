---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_PARAMETERS
title: _NDIS_RECEIVE_QUEUE_PARAMETERS (ntddndis.h)
description: The NDIS_RECEIVE_QUEUE_PARAMETERS structure contains the configuration parameters of a receive queue.
old-location: netvista\ndis_receive_queue_parameters.htm
tech.root: netvista
ms.assetid: fba87554-766d-45e2-8257-584ee78dd873
ms.date: 05/02/2018
keywords: ["NDIS_RECEIVE_QUEUE_PARAMETERS structure"]
ms.keywords: "*PNDIS_RECEIVE_QUEUE_PARAMETERS, NDIS_RECEIVE_QUEUE_PARAMETERS, NDIS_RECEIVE_QUEUE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_PARAMETERS, PNDIS_RECEIVE_QUEUE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_PARAMETERS, netvista.ndis_receive_queue_parameters, ntddndis/NDIS_RECEIVE_QUEUE_PARAMETERS, ntddndis/PNDIS_RECEIVE_QUEUE_PARAMETERS, virtual_machine_queue_ref_7c1b89fc-ccdb-4bf4-89ab-d2278be7355b.xml"
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
req.typenames: NDIS_RECEIVE_QUEUE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_PARAMETERS
f1_keywords:
 - _NDIS_RECEIVE_QUEUE_PARAMETERS
 - ntddndis/_NDIS_RECEIVE_QUEUE_PARAMETERS
 - PNDIS_RECEIVE_QUEUE_PARAMETERS
 - ntddndis/PNDIS_RECEIVE_QUEUE_PARAMETERS
 - NDIS_RECEIVE_QUEUE_PARAMETERS
 - ntddndis/NDIS_RECEIVE_QUEUE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RECEIVE_QUEUE_PARAMETERS
---

# _NDIS_RECEIVE_QUEUE_PARAMETERS structure


## -description

The **NDIS_RECEIVE_QUEUE_PARAMETERS** structure contains the configuration parameters of a receive
  queue.

## -struct-fields

### -field Header

The type, revision, and size of the **NDIS_RECEIVE_QUEUE_PARAMETERS** structure. This member is formatted as an [NDIS_OBJECT_HEADER](/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header) structure.

The miniport driver must set the **Type** member of **Header** to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the **NDIS_NIC_SWITCH_CAPABILITIES** structure, the driver must set the **Revision** member of **Header** to one of the following values:

#### NDIS_NIC_SWITCH_VPORT_PARAMETERS_REVISION_3

Added the **QosSqId** field for NDIS 6.50.

Set the **Size** member to **NDIS_SIZEOF_NIC_SWITCH_VPORT_PARAMETERS_REVISION_3**.


#### NDIS_RECEIVE_QUEUE_PARAMETERS_REVISION_2

Added additional members for NDIS 6.30.

Set the **Size** member to **NDIS_SIZEOF_RECEIVE_QUEUE_PARAMETERS_REVISION_2**.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

Set the **Size** member to **NDIS_SIZEOF_RECEIVE_QUEUE_PARAMETERS_REVISION_1**.

### -field Flags

A **ULONG** value that contains a bitwise **OR** of the following flags. The following flags are valid for the [OID_RECEIVE_FILTER_ALLOCATE_QUEUE](/windows-hardware/drivers/network/oid-receive-filter-allocate-queue) OID and the [OID_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/oid-receive-filter-queue-parameters) set and query OID:

#### NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION

The miniport driver must not mix network packets for other receive queues with the packets for this queue in a single call to the [NdisMIndicateReceiveNetBufferLists](/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists) function.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_LOOKAHEAD_SPLIT_REQUIRED

The network adapter must split a received packet at an offset equal to or greater than the requested lookahead size and use DMA to transfer the lookahead data and the post-lookahead data to separate shared memory segments.

> [!NOTE]
> Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. Miniport drivers that support NDIS 6.30 or later versions must ignore this flag.

The following flags are valid for the [OID_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/oid-receive-filter-queue-parameters) set OID and [NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/ndis-status-receive-filter-queue-parameters) status indication:

#### NDIS_RECEIVE_QUEUE_PARAMETERS_FLAGS_CHANGED

The setting in the **Flags** member changed.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_PROCESSOR_AFFINITY_CHANGED

The setting in the **ProcessorAffinity** member changed.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_SUGGESTED_RECV_BUFFER_NUMBERS_CHANGED

The setting in the **NumSuggestedReceiveBuffers** member changed.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_NAME_CHANGED

The setting in the **QueueName** member changed.

> [!NOTE]
> A driver determines which receive queue parameters have been changed by executing a bitwise **AND** operation between the **NDIS_RECEIVE_QUEUE_PARAMETERS_CHANGE_MASK** definition and the value in the **Flags** member. If the result is zero, no receive queue parameters have been changed.

### -field QueueType

An [NDIS_RECEIVE_QUEUE_TYPE](/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_receive_queue_type) enumeration value that specifies the type of the receive queue.

### -field QueueId

An **NDIS_RECEIVE_QUEUE_ID** type value that contains a receive queue identifier. This identifier is an integer value between zero and the number of queues that the network adapter supports. A value of **NDIS_DEFAULT_RECEIVE_QUEUE_ID** specifies the default receive queue.

### -field QueueGroupId

This member is reserved for NDIS.

### -field ProcessorAffinity

A **GROUP_AFFINITY** value that specifies the group number and a bitmap of the CPUs that this queue can be associated with. At least one processor must be specified. Therefore, the value must not be zero.

### -field NumSuggestedReceiveBuffers

A ULONG value that contains a suggested value for the number of receive buffers that the network adapter should use to support the queue. This number can be adjusted relative to the resources that the miniport driver has available or in proportion to the number that the network adapter uses for other queues. For example, the actual number of receive buffers can be double or half of this suggested value.

### -field MSIXTableEntry

This member is reserved for NDIS.

### -field LookaheadSize

A ULONG value for the size, in bytes, of the lookahead size requirement for this queue. A network adapter that supports lookahead in VM queues splits a received packet at an offset equal to or greater than the requested lookahead size and uses DMA to transfer the lookahead data and the post-lookahead data to separate shared memory segments. If the **LookaheadSize** is zero, the miniport driver must not split the packet.
     

**LookaheadSize** is valid when NDIS sets the **NDIS_RECEIVE_QUEUE_PARAMETERS_LOOKAHEAD_SPLIT_REQUIRED** flag in the **Flags** member. That is, the miniport driver must split the packet at the specified lookahead size if the flag is also set. If the flag is clear, a nonzero value for **LookaheadSize** is invalid.

> [!NOTE]
> Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. The value of this member must be zero.

### -field VmName

An **NDIS_VM_NAME** value that contains the description of the virtual machine that users read.

### -field QueueName

An **NDIS_QUEUE_NAME** value that contains the description of the queue that users read.

### -field PortId

A ULONG value that contains the unique identifier of a port on the Hyper-V extensible switch to which the VM queue is attached.

### -field InterruptCoalescingDomainId

This member is reserved for NDIS.

### -field QosSqId

Associates a Virtual Machine Queue (VMQ) with a Scheduler Queue (SQ). Set this field to **zero** for no SQ association. For more information on **NDIS_QOS_SQ_ID**, see [OID_QOS_OFFLOAD_CREATE_SQ](/windows-hardware/drivers/network/oid-qos-offload-create-sq.md).

Hardware Quality of Service (QoS) support for legacy VMQ is not required. The miniport driver may return NDIS_STATUS_NOT_SUPPORTED if **QosSqId** is non-zero.

## -remarks

The **NDIS_RECEIVE_QUEUE_PARAMETERS** structure is used in the [OID_RECEIVE_FILTER_ALLOCATE_QUEUE](/windows-hardware/drivers/network/oid-receive-filter-allocate-queue) OID and the [OID_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/oid-receive-filter-queue-parameters) OID.

In NDIS 6.30, the **NDIS_RECEIVE_QUEUE_PARAMETERS** structure is also used in [NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/ndis-status-receive-filter-queue-parameters) status indications.

## -see-also

[NDIS_OBJECT_HEADER](/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header)



[NDIS_RECEIVE_QUEUE_TYPE](/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_receive_queue_type)



[NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/ndis-status-receive-filter-queue-parameters)



[NdisMIndicateReceiveNetBufferLists](/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists)



[OID_RECEIVE_FILTER_ALLOCATE_QUEUE](/windows-hardware/drivers/network/oid-receive-filter-allocate-queue)



[OID_RECEIVE_FILTER_QUEUE_PARAMETERS](/windows-hardware/drivers/network/oid-receive-filter-queue-parameters)