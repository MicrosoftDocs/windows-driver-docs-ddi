---
UID: NE:ntddndis._NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
title: _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE (ntddndis.h)
description: The NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration identifies the current queue state of a receive queue.
old-location: netvista\ndis_receive_queue_operational_state.htm
tech.root: netvista
ms.assetid: a8ae7b19-9dc8-4ccc-b71e-62ec0be1fa99
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration [Network Drivers Starting with Windows Vista], NdisReceiveQueueOperationalStateDmaStopped, NdisReceiveQueueOperationalStateMaximum, NdisReceiveQueueOperationalStatePaused, NdisReceiveQueueOperationalStateRunning, NdisReceiveQueueOperationalStateUndefined, PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, netvista.ndis_receive_queue_operational_state, ntddndis/NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, ntddndis/NdisReceiveQueueOperationalStateDmaStopped, ntddndis/NdisReceiveQueueOperationalStateMaximum, ntddndis/NdisReceiveQueueOperationalStatePaused, ntddndis/NdisReceiveQueueOperationalStateRunning, ntddndis/NdisReceiveQueueOperationalStateUndefined, ntddndis/PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, virtual_machine_queue_ref_db0b16e1-5367-4a29-8a24-474aa09c07f5.xml"
ms.topic: enum
f1_keywords:
 - "ntddndis/NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE"
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
- NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
---

# _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration


## -description


The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration identifies the current queue state of a receive
  queue.


## -enum-fields




### -field NdisReceiveQueueOperationalStateUndefined

The receive queue is in the 
     Undefined state. The queue is not allocated.


### -field NdisReceiveQueueOperationalStateRunning

The receive queue is in the 
     Running state. The queue was allocated successfully, there is at least one filter set on the
     queue, and the miniport driver has completed, or will complete, the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
     OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID request with a success status.


### -field NdisReceiveQueueOperationalStatePaused

The receive queue is in the 
     Paused state. The queue was allocated successfully with the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
     OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID. There are no filters set on the queue.


### -field NdisReceiveQueueOperationalStateDmaStopped

The DMA operations on the queue are stopped because the queue is being freed, and the queue is in
     the 
     DMA Stopped state. The queue enters the 
     DMA Stopped state when the miniport driver receives an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-free-queue">
     OID_RECEIVE_FILTER_FREE_QUEUE</a> OID request, stops the DMA operations for the queue, and issues an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_queue_state">
     NDIS_STATUS_RECEIVE_QUEUE_STATE</a> status indication.


### -field NdisReceiveQueueOperationalStateMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_queue_state">NDIS_RECEIVE_QUEUE_STATE</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_receive_queue_info">
    NDIS_RECEIVE_QUEUE_INFO</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_receive_queue_info">NDIS_RECEIVE_QUEUE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_queue_state">NDIS_RECEIVE_QUEUE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_queue_state">
   NDIS_STATUS_RECEIVE_QUEUE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
   OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-free-queue">OID_RECEIVE_FILTER_FREE_QUEUE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>
 

 

