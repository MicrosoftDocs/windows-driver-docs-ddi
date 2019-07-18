---
UID: NS:ndis._NDIS_PD_QUEUE_PARAMETERS
title: _NDIS_PD_QUEUE_PARAMETERS (ndis.h)
description: This structure is used to hold parameters for a transmit or receive queue when calling any of the queue routines.
old-location: netvista\ndis_pd_queue_parameters.htm
tech.root: netvista
ms.assetid: AE9110D8-FB13-43DA-8BAA-8DD88CA3492A
ms.date: 05/02/2018
ms.keywords: NDIS_PD_QUEUE_PARAMETERS, NDIS_PD_QUEUE_PARAMETERS structure [Network Drivers Starting with Windows Vista], _NDIS_PD_QUEUE_PARAMETERS, ndis/NDIS_PD_QUEUE_PARAMETERS, netvista.ndis_pd_queue_parameters
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_PD_QUEUE_PARAMETERS"
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- Ndis.h
api_name:
- NDIS_PD_QUEUE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_QUEUE_PARAMETERS
---

# _NDIS_PD_QUEUE_PARAMETERS structure


## -description


This structure is used to hold parameters for a transmit or receive queue when calling any of the queue routines.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pd_config">NDIS_PD_CONFIG</a> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_QUEUE_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_QUEUE_PARAMETERS_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0 by the provider.


### -field QueueType

The type of the queue. For more information see, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ne-ndis-ndis_pd_queue_type">NDIS_PD_QUEUE_TYPE</a>.


### -field QueueSize

The maximum amount of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures this queue can hold and is always equal to a number of the form (2^k)-1 (63, 127, 255, 511, 1023, etc.). This lends itself to efficient circular index arithmetic.


### -field ReceiveDataLength

The minimum <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> data length.


### -field Affinity

The processor affinity is a hint to the provider for performance optimization. The platform will primarily be processing the queue on processors indicated by this mask. The provider must set this value to the processor core derived from the indirection table configured from <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters">OID_GEN_RECEIVE_SCALE_PARAMETERS</a>



### -field TrafficClassId

 


### -field MaximumPartialBufferCount

For transmit queues, this is the maximum number of partial <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures that the client is allowed to chain together to form a single L2 packet. This value must be equal to the MaximumTxPartialBufferCount value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pd_capabilities">NDIS_PD_CAPABILITIES</a> structure.

For receive queues, this is the maximum number of partial <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures that the provider is allowed to chain together to form a single large L2 packet with RSC. This must be less than or equal to the MaximumRxPartialBufferCount value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pd_capabilities">NDIS_PD_CAPABILITIES</a> structure.

<div class="alert"><b>Note</b>  The client never posts <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures with the partial flag to the receive queue. The client is always required to post <b>PD_BUFFER</b> structures with at least MTU-size space, starting from the data start position. The provider performs chaining only in the case of RSC. Some providers may not be able to support RSC chaining, these providers set a value of 1 to the MaximumRxPartialBufferCount member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_pd_capabilities">NDIS_PD_CAPABILITIES</a> structure.</div>
<div> </div>

### -field CounterHandle

This is a handle to the transmit queue counter for transmit queues and a receive queue counter for receive queues.During queue creation, a client can optionally provide a counter handle. In this case and depending on the queue type, the provider must update the counter values as activity occurs on the queue. The client is responsible for closing the counter handle only after the queue is closed.

For queues that are not directly created by the client, such as RSS receive queues obtained using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/index">NdisPDOnRssReceiveQueues</a>routine, the provider must always have an associated counter handle with the queue. That is, for a given set of RSS receive queues, the provider must have one dedicated receive queue counter for each receive queue.


#### - UserPriority

Used by the provider to determine the traffic class for the queue.


## -remarks



This structure must be aligned on an 8-byte boundary.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ne-ndis-ndis_pd_queue_type">NDIS_PD_QUEUE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-ndis_pd_allocate_queue">NdisPDAllocateQueue</a>
 

 

