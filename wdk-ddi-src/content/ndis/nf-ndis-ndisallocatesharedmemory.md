---
UID: NF:ndis.NdisAllocateSharedMemory
title: NdisAllocateSharedMemory function
author: windows-driver-content
description: The NdisAllocateSharedMemory function allocates shared memory from a shared memory provider.
old-location: netvista\ndisallocatesharedmemory.htm
old-project: netvista
ms.assetid: 1e4919df-7897-44c3-876f-0f1acfe6d5af
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAllocateSharedMemory, NdisAllocateSharedMemory function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateSharedMemory, ndis_shared_memory_ref_252ce78e-6920-4825-9537-c1ddd2f9f900.xml, netvista.ndisallocatesharedmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisAllocateSharedMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateSharedMemory function


## -description


The 
  <b>NdisAllocateSharedMemory</b> function allocates shared memory from a shared memory provider.


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> or 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



### -param SharedMemoryParameters [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/286b08f6-179e-426e-ae65-b108529d049a">
     NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
     memory.


### -param pAllocationHandle [in, out]

A pointer to a location for a handle that identifies the shared memory that was allocated. The
     handle is available when the function returns or it is <b>NULL</b> if the function fails. The caller must use
     this handle to free the shared memory that was allocated successfully.


## -returns



<b>NdisAllocateSharedMemory</b> can return the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because there were insufficient resources to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of an invalid input parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The operation failed for unspecified reasons.

</td>
</tr>
</table>
 




## -remarks



<div class="alert"><b>Note</b>  A miniport driver must have already called <a href="https://msdn.microsoft.com/library/windows/hardware/ff563659">NdisMRegisterScatterGatherDma</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563646">NdisMRegisterDmaChannel</a> to initialize a
  scatter/gather DMA channel before calling <b>NdisAllocateSharedMemory</b>.</div>
<div> </div>
NDIS drivers call the 
    <b>NdisAllocateSharedMemory</b> function to allocate a block of shared memory from an NDIS shared memory
    provider.

The 
    <i>SharedMemoryParameters</i> parameter contains a pointer to an 
    <a href="https://msdn.microsoft.com/286b08f6-179e-426e-ae65-b108529d049a">
    NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
    memory. If the <b>NDIS_SHARED_MEM_PARAMETERS_CONTIGUOUS</b> flag is not set in the 
    <b>Flags</b> member, shared memory can be specified in a scatter-gather list that is contained in
    non-contiguous memory.

NDIS calls the 
    <a href="https://msdn.microsoft.com/d85b4f28-707b-4525-afd8-83e1ceb2674e">NetAllocateSharedMemory</a> function of a shared memory provider from the context of the call to 
    <b>NdisAllocateSharedMemory</b>.

The driver must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562601">NdisFreeSharedMemory</a> function to free
    the shared memory that it allocates with 
    <b>NdisAllocateSharedMemory</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567303">NDIS_SHARED_MEMORY_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562601">NdisFreeSharedMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563646">NdisMRegisterDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
   NdisMRegisterScatterGatherDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/d85b4f28-707b-4525-afd8-83e1ceb2674e">NetAllocateSharedMemory</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateSharedMemory function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
