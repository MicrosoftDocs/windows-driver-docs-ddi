---
UID: NS:ndis._NDIS_RECEIVE_QUEUE_STATE
title: _NDIS_RECEIVE_QUEUE_STATE (ndis.h)
description: The NDIS_RECEIVE_QUEUE_STATE structure contains information about the operational state of a receive queue.
old-location: netvista\ndis_receive_queue_state.htm
tech.root: netvista
ms.assetid: e997fce6-ee3a-433f-b9b7-3e2932093a1a
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_STATE, NDIS_RECEIVE_QUEUE_STATE, NDIS_RECEIVE_QUEUE_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_STATE, PNDIS_RECEIVE_QUEUE_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_STATE, ndis/NDIS_RECEIVE_QUEUE_STATE, ndis/PNDIS_RECEIVE_QUEUE_STATE, netvista.ndis_receive_queue_state, virtual_machine_queue_ref_4cbbc25f-cd33-45d7-b279-1661570110f0.xml"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_RECEIVE_QUEUE_STATE"
req.header: ndis.h
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
- Ndis.h
api_name:
- NDIS_RECEIVE_QUEUE_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_STATE, *PNDIS_RECEIVE_QUEUE_STATE
---

# _NDIS_RECEIVE_QUEUE_STATE structure


## -description


The <b>NDIS_RECEIVE_QUEUE_STATE</b> structure contains information about the operational state of a receive
  queue.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_STATE</b>  structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_STATE_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_RECEIVE_QUEUE_STATE_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a queue identifier. The queue identifier is an
     integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies
     the default receive queue.


### -field QueueState

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_receive_queue_operational_state">NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a> enumeration value that specifies the operational state of the
     receive queue.


## -remarks



The <b>NDIS_RECEIVE_QUEUE_STATE</b> structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_queue_state">
    NDIS_STATUS_RECEIVE_QUEUE_STATE</a> status indication.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_receive_queue_operational_state">
   NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_receive_queue_state">
   NDIS_STATUS_RECEIVE_QUEUE_STATE</a>
 

 

