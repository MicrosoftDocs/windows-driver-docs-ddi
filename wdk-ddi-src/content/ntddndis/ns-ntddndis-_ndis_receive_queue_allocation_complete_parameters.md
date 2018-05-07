---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS
title: "_NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure contains information about the allocation status of a receive queue.
old-location: netvista\ndis_receive_queue_allocation_complete_parameters.htm
old-project: netvista
ms.assetid: 1aae1bc7-24c6-46a3-be0e-f028d6b70774
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, netvista.ndis_receive_queue_allocation_complete_parameters, ntddndis/NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, ntddndis/PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, virtual_machine_queue_ref_6427710d-2634-40e1-bd03-a93fdedfd5a3.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS
---

# _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</b> structure contains information about the
  allocation status of a receive queue.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a receive queue identifier. This identifier is an integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies the default receive queue.


### -field CompletionStatus

An <b>NDIS_STATUS</b> value that contains an NDIS_STATUS_<i>Xxx</i> completion status code. The miniport driver
     provides this status code to indicate the completion status of a queue. The miniport driver can use
     <b>NDIS_STATUS_SUCCESS</b> if the allocation succeeded. Otherwise the miniport driver can use an appropriate
     error status, for example, <b>NDIS_STATUS_RESOURCES</b>.


## -remarks



The <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</b> structure is used with the 
    <a href="https://msdn.microsoft.com/f071569f-fa99-4614-96a7-edf73a85d96a">
    NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</a> structure and the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
    OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/f071569f-fa99-4614-96a7-edf73a85d96a">
   NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>
 

 

