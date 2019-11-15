---
UID: NF:ndis.NdisFreeSharedMemory
title: NdisFreeSharedMemory function (ndis.h)
description: The NdisFreeSharedMemory function frees shared memory that a driver allocated from a shared memory provider.
old-location: netvista\ndisfreesharedmemory.htm
tech.root: netvista
ms.assetid: 5d0a1790-cec0-4c28-85dd-5f4d7d518d63
ms.date: 05/02/2018
ms.keywords: NdisFreeSharedMemory, NdisFreeSharedMemory function [Network Drivers Starting with Windows Vista], ndis/NdisFreeSharedMemory, ndis_shared_memory_ref_b020f3ba-6e10-422f-9342-650236ace5f8.xml, netvista.ndisfreesharedmemory
ms.topic: function
f1_keywords:
 - "ndis/NdisFreeSharedMemory"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFreeSharedMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeSharedMemory function


## -description


The 
  <b>NdisFreeSharedMemory</b> function frees shared memory that a driver allocated from a shared memory
  provider.


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that was passed to the 
     <i>NdisHandle</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">
     NdisAllocateSharedMemory</a> function when the shared memory was allocated.


### -param AllocationHandle [in]

A handle for a context area that identifies the shared memory block. This is the handle that NDIS
     supplied at the 
     <i>pSharedMemoryProviderContext</i> parameter of the 
     <b>NdisAllocateSharedMemory</b> function.


## -remarks



An NDIS driver must call the 
    <b>NdisFreeSharedMemory</b> function to free a block of shared memory that it previously allocated with
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">
    NdisAllocateSharedMemory</a> function.

NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-free_shared_memory_handler">NetFreeSharedMemory</a> function of a
    shared memory provider from the context of the call to 
    <b>NdisFreeSharedMemory</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatesharedmemory">NdisAllocateSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-free_shared_memory_handler">NetFreeSharedMemory</a>
 

 

