---
UID: NC:ndis.ALLOCATE_SHARED_MEMORY_HANDLER
title: ALLOCATE_SHARED_MEMORY_HANDLER (ndis.h)
description: The NetAllocateSharedMemory function (ALLOCATE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver allocates shared memory from a shared memory provider.
old-location: netvista\netallocatesharedmemory.htm
tech.root: netvista
ms.assetid: d85b4f28-707b-4525-afd8-83e1ceb2674e
ms.date: 05/02/2018
ms.keywords: ALLOCATE_SHARED_MEMORY_HANDLER, ALLOCATE_SHARED_MEMORY_HANDLER callback, NetAllocateSharedMemory, NetAllocateSharedMemory callback function [Network Drivers Starting with Windows Vista], ndis/NetAllocateSharedMemory, ndis_shared_memory_ref_8830fb4b-2e73-4994-91c6-a885d1c0ef74.xml, netvista.netallocatesharedmemory
ms.topic: callback
f1_keywords:
 - "ndis/NetAllocateSharedMemory"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- NetAllocateSharedMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# ALLOCATE_SHARED_MEMORY_HANDLER callback function


## -description


The 
  <i>NetAllocateSharedMemory</i> function (ALLOCATE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when
  a driver allocates shared memory from a shared memory provider.


## -parameters




### -param ProviderContext [in]

An NDIS_HANDLE to a block of driver-allocated context information that identifies the provider.
     The provider supplied this information in the 
     <b>ProviderContext</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_provider_characteristics">
     NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.


### -param SharedMemoryParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">
     NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
     memory.


### -param pSharedMemoryProviderContext [in, out]

A pointer to a handle for a shared memory context area. The shared memory provider provides a
     handle that identifies the shared memory that it allocated.


## -returns



<i>NetAllocateSharedMemory</i> can return the following status values:

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



NDIS calls the 
    <i>NetAllocateSharedMemory</i> function of a shared memory provider when a driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">
    NdisAllocateSharedMemory</a> function.

The shared memory provider specified the entry point (ALLOCATE_SHARED_MEMORY_HANDLER) for 
    <i>NetAllocateSharedMemory</i> in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_provider_characteristics">
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">NDIS_SHARED_MEMORY_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_provider_characteristics">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">NdisAllocateSharedMemory</a>
 

 

