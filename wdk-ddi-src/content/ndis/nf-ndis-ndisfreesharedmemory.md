---
UID: NF:ndis.NdisFreeSharedMemory
title: NdisFreeSharedMemory function
author: windows-driver-content
description: The NdisFreeSharedMemory function frees shared memory that a driver allocated from a shared memory provider.
old-location: netvista\ndisfreesharedmemory.htm
old-project: netvista
ms.assetid: 5d0a1790-cec0-4c28-85dd-5f4d7d518d63
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFreeSharedMemory, NdisFreeSharedMemory function [Network Drivers Starting with Windows Vista], ndis/NdisFreeSharedMemory, ndis_shared_memory_ref_b020f3ba-6e10-422f-9342-650236ace5f8.xml, netvista.ndisfreesharedmemory
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
-	NdisFreeSharedMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeSharedMemory function


## -description


The 
  <b>NdisFreeSharedMemory</b> function frees shared memory that a driver allocated from a shared memory
  provider.


## -syntax


````
VOID NdisFreeSharedMemory(
  _In_ NDIS_HANDLE NdisHandle,
  _In_ NDIS_HANDLE AllocationHandle
);
````


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that was passed to the 
     <i>NdisHandle</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisallocatesharedmemory.md">
     NdisAllocateSharedMemory</a> function when the shared memory was allocated.


### -param AllocationHandle [in]

A handle for a context area that identifies the shared memory block. This is the handle that NDIS
     supplied at the 
     <i>pSharedMemoryProviderContext</i> parameter of the 
     <b>NdisAllocateSharedMemory</b> function.


## -returns



None




## -remarks



An NDIS driver must call the 
    <b>NdisFreeSharedMemory</b> function to free a block of shared memory that it previously allocated with
    the 
    <a href="..\ndis\nf-ndis-ndisallocatesharedmemory.md">
    NdisAllocateSharedMemory</a> function.

NDIS calls the 
    <a href="..\ndis\nc-ndis-free_shared_memory_handler.md">NetFreeSharedMemory</a> function of a
    shared memory provider from the context of the call to 
    <b>NdisFreeSharedMemory</b>.




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatesharedmemory.md">NdisAllocateSharedMemory</a>



<a href="..\ndis\nc-ndis-free_shared_memory_handler.md">NetFreeSharedMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeSharedMemory function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

