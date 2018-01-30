---
UID: NE:ntddndis._NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
title: "_NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration identifies the current queue state of a receive queue.
old-location: netvista\ndis_receive_queue_operational_state.htm
old-project: netvista
ms.assetid: a8ae7b19-9dc8-4ccc-b71e-62ec0be1fa99
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, netvista.ndis_receive_queue_operational_state, ntddndis/NdisReceiveQueueOperationalStateRunning, ntddndis/NdisReceiveQueueOperationalStateUndefined, NdisReceiveQueueOperationalStatePaused, ntddndis/NdisReceiveQueueOperationalStateDmaStopped, ntddndis/PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NdisReceiveQueueOperationalStateMaximum, ntddndis/NdisReceiveQueueOperationalStateMaximum, PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration pointer [Network Drivers Starting with Windows Vista], *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, ntddndis/NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, ntddndis/NdisReceiveQueueOperationalStatePaused, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration [Network Drivers Starting with Windows Vista], NdisReceiveQueueOperationalStateUndefined, NdisReceiveQueueOperationalStateDmaStopped, NdisReceiveQueueOperationalStateRunning, virtual_machine_queue_ref_db0b16e1-5367-4a29-8a24-474aa09c07f5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
product: Windows
targetos: Windows
req.typenames: "*PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE"
---

# _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration


## -description


The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration identifies the current queue state of a receive
  queue.


## -syntax


````
typedef enum _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE { 
  NdisReceiveQueueOperationalStateUndefined,
  NdisReceiveQueueOperationalStateRunning,
  NdisReceiveQueueOperationalStatePaused,
  NdisReceiveQueueOperationalStateDmaStopped,
  NdisReceiveQueueOperationalStateMaximum
} NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE;
````


## -enum-fields




### -field NdisReceiveQueueOperationalStateUndefined

The receive queue is in the 
     Undefined state. The queue is not allocated.


### -field NdisReceiveQueueOperationalStateRunning

The receive queue is in the 
     Running state. The queue was allocated successfully, there is at least one filter set on the
     queue, and the miniport driver has completed, or will complete, the 
     <mshelp:link keywords="netvista.oid_receive_filter_queue_allocation_complete" tabindex="0">
     OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</mshelp:link> OID request with a success status.


### -field NdisReceiveQueueOperationalStatePaused

The receive queue is in the 
     Paused state. The queue was allocated successfully with the 
     <mshelp:link keywords="netvista.oid_receive_filter_allocate_queue" tabindex="0">
     OID_RECEIVE_FILTER_ALLOCATE_QUEUE</mshelp:link> OID. There are no filters set on the queue.


### -field NdisReceiveQueueOperationalStateDmaStopped

The DMA operations on the queue are stopped because the queue is being freed, and the queue is in
     the 
     DMA Stopped state. The queue enters the 
     DMA Stopped state when the miniport driver receives an 
     <mshelp:link keywords="netvista.oid_receive_filter_free_queue" tabindex="0">
     OID_RECEIVE_FILTER_FREE_QUEUE</mshelp:link> OID request, stops the DMA operations for the queue, and issues an 
     <mshelp:link keywords="netvista.ndis_status_receive_queue_state" tabindex="0"><b>
     NDIS_STATUS_RECEIVE_QUEUE_STATE</b></mshelp:link> status indication.


### -field NdisReceiveQueueOperationalStateMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration is used in the 
    <a href="..\ndis\ns-ndis-_ndis_receive_queue_state.md">NDIS_RECEIVE_QUEUE_STATE</a> and 
    <mshelp:link keywords="netvista.ndis_receive_queue_info" tabindex="0"><b>
    NDIS_RECEIVE_QUEUE_INFO</b></mshelp:link> structures.



## -see-also

<a href="..\ndis\ns-ndis-_ndis_receive_queue_state.md">NDIS_RECEIVE_QUEUE_STATE</a>

<mshelp:link keywords="netvista.oid_receive_filter_allocate_queue" tabindex="0">
   OID_RECEIVE_FILTER_ALLOCATE_QUEUE</mshelp:link>

<mshelp:link keywords="netvista.ndis_status_receive_queue_state" tabindex="0"><b>
   NDIS_STATUS_RECEIVE_QUEUE_STATE</b></mshelp:link>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-free-queue">OID_RECEIVE_FILTER_FREE_QUEUE</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_info.md">NDIS_RECEIVE_QUEUE_INFO</a>

<mshelp:link keywords="netvista.oid_receive_filter_queue_allocation_complete" tabindex="0">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

