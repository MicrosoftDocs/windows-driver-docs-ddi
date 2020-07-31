---
UID: NS:ndis._NDIS_SHARED_MEMORY_PARAMETERS
title: _NDIS_SHARED_MEMORY_PARAMETERS (ndis.h)
description: The NDIS_SHARED_MEMORY_PARAMETERS structure specifies the shared memory parameters for a shared memory allocation request.
old-location: netvista\ndis_shared_memory_parameters.htm
tech.root: netvista
ms.assetid: 286b08f6-179e-426e-ae65-b108529d049a
ms.date: 05/02/2018
keywords: ["_NDIS_SHARED_MEMORY_PARAMETERS structure"]
ms.keywords: "*PNDIS_SHARED_MEMORY_PARAMETERS, NDIS_SHARED_MEMORY_PARAMETERS, NDIS_SHARED_MEMORY_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SHARED_MEMORY_PARAMETERS, PNDIS_SHARED_MEMORY_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SHARED_MEMORY_PARAMETERS, ndis/NDIS_SHARED_MEMORY_PARAMETERS, ndis/PNDIS_SHARED_MEMORY_PARAMETERS, ndis_shared_memory_ref_76b2c89f-c221-42de-ae92-ad10cf2297f2.xml, netvista.ndis_shared_memory_parameters"
f1_keywords:
 - "ndis/NDIS_SHARED_MEMORY_PARAMETERS"
 - "NDIS_SHARED_MEMORY_PARAMETERS"
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
- NDIS_SHARED_MEMORY_PARAMETERS
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_PARAMETERS, *PNDIS_SHARED_MEMORY_PARAMETERS
---

# _NDIS_SHARED_MEMORY_PARAMETERS structure


## -description


The NDIS_SHARED_MEMORY_PARAMETERS structure specifies the shared memory parameters for a shared
  memory allocation request.


## -struct-fields




### -field Header

The type, revision, and size of the NDIS_SHARED_MEMORY_PARAMETERS structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the NDIS_SHARED_MEMORY_PARAMETERS structure, the driver must set the <b>Revision</b> member of <b>Header</b> to one of the following values: 





#### NDIS_SHARED_MEMORY_PARAMETERS_REVISION_2

Added <b>VPortId</b> for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_SHARED_MEMORY_PARAMETERS_REVISION_2.



#### NDIS_SHARED_MEMORY_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_SHARED_MEMORY_PARAMETERS_REVISION_1.


### -field Flags

A UCHAR value that contains a bitwise OR of the following value:
     





#### NDIS_SHARED_MEM_PARAMETERS_CONTIGOUS

The shared memory is in a contiguous block of memory.


### -field QueueId

An NDIS_RECEIVE_QUEUE_ID value that contains a virtual machine queue (VMQ) or single root I/O virtualization (SR-IOV) receive queue identifier. This identifier is an
     integer between zero and the number of queues that the miniport adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface only supports the default receive queue on both default and nondefault virtual ports (VPorts). Miniport drivers that support the SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field SharedMemoryHandle

An NDIS_HANDLE value that identifies a block of shared memory. NDIS provides this handle before it
     returns from the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">
     NdisAllocateSharedMemory</a> function.


### -field PreferredNode

A NODE_REQUIREMENT value that indicates the preferred node to use while allocating memory. If the driver does not have a preference, then the value must be set to MM_ANY_NODE_OK.


### -field Usage

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_shared_memory_usage">NDIS_SHARED_MEMORY_USAGE</a> enumeration
     value that specifies the purpose of the shared memory.


### -field Length

A ULONG value that contains the length, in bytes, of the shared memory block.


### -field VirtualAddress

A PVOID value that contains the base virtual address of the shared memory. NDIS provides this
     value before it returns from the 
     <b>NdisAllocateSharedMemory</b> function.


### -field SGListBufferLength

A ULONG value that contains the length, in bytes, of the scatter gather list buffer.


### -field SGListBuffer

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure.


### -field VPortId

An NDIS_NIC_SWITCH_VPORT_ID value that specifies a virtual port (VPort) identifier on which the shared memory is to be allocated. This value must be the identifier of a nondefault VPort that is attached to the physical function (PF) of the miniport adapter. 



<div class="alert"><b>Note</b>  Miniport drivers that support the VMQ interface must set this member to zero. Miniport drivers that support the SR-IOV interface must not set this member to zero (DEFAULT_VPORT_ID).</div>
<div> </div>

## -remarks



The NDIS_SHARED_MEMORY_PARAMETERS structure specifies the shared memory parameters for a shared memory
    allocation request for a receive queue.

NDIS drivers pass this structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">NdisAllocateSharedMemory</a> function
    and NDIS passes this structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">NetAllocateSharedMemory</a> function
    (ALLOCATE_SHARED_MEMORY_HANDLER entry point).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_shared_memory_usage">NDIS_SHARED_MEMORY_USAGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">NdisAllocateSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">NetAllocateSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
 

 

