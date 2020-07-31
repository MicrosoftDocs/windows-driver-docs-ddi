---
UID: NS:ndis._NDIS_SCATTER_GATHER_LIST_PARAMETERS
title: _NDIS_SCATTER_GATHER_LIST_PARAMETERS (ndis.h)
description: The NDIS_SCATTER_GATHER_LIST_PARAMETERS structure specifies parameters that NDIS uses to build a scatter/gather list for a buffer.
old-location: netvista\ndis_scatter_gather_list_parameters.htm
tech.root: netvista
ms.assetid: 5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36
ms.date: 05/02/2018
keywords: ["_NDIS_SCATTER_GATHER_LIST_PARAMETERS structure"]
ms.keywords: "*PNDIS_SCATTER_GATHER_LIST_PARAMETERS, NDIS_SCATTER_GATHER_LIST_PARAMETERS, NDIS_SCATTER_GATHER_LIST_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SCATTER_GATHER_LIST_PARAMETERS, PNDIS_SCATTER_GATHER_LIST_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SCATTER_GATHER_LIST_PARAMETERS, ndis/NDIS_SCATTER_GATHER_LIST_PARAMETERS, ndis/PNDIS_SCATTER_GATHER_LIST_PARAMETERS, ndis_shared_memory_ref_b74a7da6-25c0-4ede-8540-d8fd5ee88ca2.xml, netvista.ndis_scatter_gather_list_parameters"
f1_keywords:
 - "ndis/NDIS_SCATTER_GATHER_LIST_PARAMETERS"
 - "NDIS_SCATTER_GATHER_LIST_PARAMETERS"
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
- ndis.h
api_name:
- NDIS_SCATTER_GATHER_LIST_PARAMETERS
targetos: Windows
req.typenames: NDIS_SCATTER_GATHER_LIST_PARAMETERS, *PNDIS_SCATTER_GATHER_LIST_PARAMETERS
---

# _NDIS_SCATTER_GATHER_LIST_PARAMETERS structure


## -description


The NDIS_SCATTER_GATHER_LIST_PARAMETERS structure specifies parameters that NDIS uses to build a
  scatter/gather list for a buffer.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_SCATTER_GATHER_LIST_PARAMETERS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SCATTER_GATHER_LIST_PARAMETERS_REVISION_1 and the 
     <b>Size</b> member to NDIS_SIZEOF_SCATTER_GATHER_LIST_PARAMETERS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field QueueId

An NDIS_RECEIVE_QUEUE_ID type value that contains a queue identifier. The queue identifier is an
     integer between zero and the number of queues that the miniport adapter supports. A zero value indicates
     the default queue.


### -field SharedMemoryUsage

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_shared_memory_usage">NDIS_SHARED_MEMORY_USAGE</a> enumeration
     value that specifies the purpose of the shared memory.


### -field Mdl

A pointer to a memory descriptor list (MDL) that describes the shared memory buffer.


### -field CurrentVa

A ULONG value for the current virtual address.


### -field Length

A ULONG value that contains the length, in bytes, of the shared memory buffer.


### -field ProcessSGListHandler

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_process_sg_list">NetProcessSGList</a> function
     (NDIS_PROCESS_SG_LIST_HANDLER entry point).


### -field Context

A pointer to a block of driver-allocated context information that stores information about the
     scatter/gather list. NDIS passes the context information in calls to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_process_sg_list">NetProcessSGList</a> at the 
     <i>Context</i> parameter.


### -field ScatterGatherListBuffer

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure.


### -field ScatterGatherListBufferSize

A ULONG value that contains the length, in bytes, of the scatter/gather list.


### -field ScatterGatherListBufferSizeNeeded

A ULONG value where NDIS writes the total number of bytes that NDIS requires to build the
     scatter/gather list successfully.


## -remarks



To build a scatter/gather list, an NDIS driver passes the NDIS_SCATTER_GATHER_LIST_PARAMETERS
    structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisbuildscattergatherlist">
    NdisBuildScatterGatherList</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_shared_memory_usage">NDIS_SHARED_MEMORY_USAGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisbuildscattergatherlist">NdisBuildScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_process_sg_list">NetProcessSGList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
 

 

