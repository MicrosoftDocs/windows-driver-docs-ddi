---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_PARAMETERS
title: "_NDIS_RECEIVE_QUEUE_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_PARAMETERS structure contains the configuration parameters of a receive queue.
old-location: netvista\ndis_receive_queue_parameters.htm
tech.root: netvista
ms.assetid: fba87554-766d-45e2-8257-584ee78dd873
ms.date: 5/2/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_PARAMETERS, NDIS_RECEIVE_QUEUE_PARAMETERS, NDIS_RECEIVE_QUEUE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_PARAMETERS, PNDIS_RECEIVE_QUEUE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_PARAMETERS, netvista.ndis_receive_queue_parameters, ntddndis/NDIS_RECEIVE_QUEUE_PARAMETERS, ntddndis/PNDIS_RECEIVE_QUEUE_PARAMETERS, virtual_machine_queue_ref_7c1b89fc-ccdb-4bf4-89ab-d2278be7355b.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_QUEUE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_PARAMETERS
---

# _NDIS_RECEIVE_QUEUE_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure contains the configuration parameters of a receive
  queue.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to one of the following values: 





#### NDIS_RECEIVE_QUEUE_PARAMETERS_REVISION_2

Added additional members for NDIS 6.30.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_PARAMETERS_REVISION_2</b>.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_PARAMETERS_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of the following flags. The following flags are valid for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
     OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID and the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-parameters">
     OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a> set and query OID:





#### NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION

The miniport driver must not mix network packets for other receive queues with the packets for
       this queue in a single call to the 
       <a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
       NdisMIndicateReceiveNetBufferLists</a> function.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_LOOKAHEAD_SPLIT_REQUIRED

The network adapter must split a received packet at an offset equal to or greater than the
       requested lookahead size and use DMA to transfer the lookahead data and the post-lookahead data to
       separate shared memory segments.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. Miniport drivers that support NDIS 6.30 or later versions must ignore this flag.</div>

The following flags are valid for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-parameters">
     OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a> set OID and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439820">NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS</a> status indication:

#### NDIS_RECEIVE_QUEUE_PARAMETERS_FLAGS_CHANGED

The setting in the 
       <b>Flags</b> member changed.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_PROCESSOR_AFFINITY_CHANGED

The setting in the 
       <b>ProcessorAffinity</b> member changed.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_SUGGESTED_RECV_BUFFER_NUMBERS_CHANGED

The setting in the 
       <b>NumSuggestedReceiveBuffers</b> member changed.



#### NDIS_RECEIVE_QUEUE_PARAMETERS_NAME_CHANGED

The setting in the 
       <b>QueueName</b> member changed.

<div class="alert"><b>Note</b>  A driver determines which receive queue parameters have been changed by executing a bitwise <b>AND</b> operation between the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_CHANGE_MASK</b> definition and the value in the <b>Flags</b> member. If the result is zero, no receive queue parameters have been changed.</div>

### -field QueueType

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff567217">NDIS_RECEIVE_QUEUE_TYPE</a> enumeration
     value that specifies the type of the receive queue.


### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a receive queue identifier. This identifier is an integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies the default receive queue.


### -field QueueGroupId

This member is reserved for NDIS.


### -field ProcessorAffinity

A <b>GROUP_AFFINITY</b> value that specifies the group number and a bitmap of the CPUs that this queue
     can be associated with. At least one processor must be specified. Therefore, the value must not be
     zero.


### -field NumSuggestedReceiveBuffers

A <b>ULONG</b> value that contains a suggested value for the number of receive buffers that the network adapter should use to support the queue. This number can be adjusted relative to the resources that the
     miniport driver has available or in proportion to the number that the network adapter uses for other
     queues. For example, the actual number of receive buffers can be double or half of this suggested
     value.


### -field MSIXTableEntry

This member is reserved for NDIS.


### -field LookaheadSize

A <b>ULONG</b> value for the size, in bytes, of the lookahead size requirement for this queue. A network adapter that supports lookahead in VM queues splits a received packet at an offset equal to or greater
     than the requested lookahead size and uses DMA to transfer the lookahead data and the post-lookahead
     data to separate shared memory segments. If the 
     <b>LookaheadSize</b> is zero, the miniport driver must not split the packet.
     

<b>LookaheadSize</b> is valid when NDIS sets the
     <b>NDIS_RECEIVE_QUEUE_PARAMETERS_LOOKAHEAD_SPLIT_REQUIRED</b> flag in the <b>Flags</b> member. That is, the miniport driver must split
     the packet at the specified lookahead size if the flag is also set. If the flag is clear, a nonzero
     value for 
     <b>LookaheadSize</b> is invalid.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. The value of this member must be zero.</div>

### -field VmName

An <b>NDIS_VM_NAME</b> value that contains the description of the virtual machine that users read.


### -field QueueName

An <b>NDIS_QUEUE_NAME</b> value that contains the description of the queue that users read.


### -field PortId

A ULONG value that contains the unique identifier of a port on the Hyper-V extensible switch to which the VM queue is attached.




### -field InterruptCoalescingDomainId

This member is reserved for NDIS.


### -field QosSqId

 




## -remarks



The <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
    OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID and the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-parameters">
    OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a> OID.

In NDIS 6.30, the <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure is also used in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439820">NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS</a> status indications.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567217">NDIS_RECEIVE_QUEUE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439820">NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
   OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-parameters">
   OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a>
 

 

