---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS
title: "_NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure contains information about the allocation status of a receive queue.
old-location: netvista\ndis_receive_queue_allocation_complete_parameters.htm
old-project: netvista
ms.assetid: 1aae1bc7-24c6-46a3-be0e-f028d6b70774
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: virtual_machine_queue_ref_6427710d-2634-40e1-bd03-a93fdedfd5a3.xml, ntddndis/NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, netvista.ndis_receive_queue_allocation_complete_parameters, ntddndis/PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista]
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS
---

# _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</b> structure contains information about the
  allocation status of a receive queue.


## -syntax


````
typedef struct _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 Flags;
  NDIS_RECEIVE_QUEUE_ID QueueId;
  NDIS_STATUS           CompletionStatus;
} NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
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
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_allocation_complete_array.md">
    NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</a> structure and the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
    OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_allocation_complete_array.md">
   NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

