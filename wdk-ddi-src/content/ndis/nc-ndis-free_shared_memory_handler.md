---
UID: NC:ndis.FREE_SHARED_MEMORY_HANDLER
title: FREE_SHARED_MEMORY_HANDLER (ndis.h)
description: The NetFreeSharedMemory function (FREE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver frees shared memory from a shared memory provider.
old-location: netvista\netfreesharedmemory.htm
tech.root: netvista
ms.assetid: fdc3dfe7-6980-493d-ad41-aed501db3a6b
ms.date: 05/02/2018
keywords: ["FREE_SHARED_MEMORY_HANDLER callback function"]
ms.keywords: FREE_SHARED_MEMORY_HANDLER, FREE_SHARED_MEMORY_HANDLER callback, NetFreeSharedMemory, NetFreeSharedMemory callback function [Network Drivers Starting with Windows Vista], ndis/NetFreeSharedMemory, ndis_shared_memory_ref_15b5aca1-e5be-4063-812f-9d98a4e72cd4.xml, netvista.netfreesharedmemory
f1_keywords:
 - "ndis/NetFreeSharedMemory"
 - "NetFreeSharedMemory"
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
- NetFreeSharedMemory
targetos: Windows
req.typenames: 
---

# FREE_SHARED_MEMORY_HANDLER callback function


## -description


The 
  <i>NetFreeSharedMemory</i> function (FREE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver
  frees shared memory from a shared memory provider.


## -parameters




### -param ProviderContext 
[in]
An NDIS_HANDLE to a block of driver-allocated context information that identifies the provider.
     The provider supplied this information in the 
     <b>ProviderContext</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_provider_characteristics">
     NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.


### -param SharedMemoryProviderContext 
[in]
A handle for a context area that identifies the shared memory block. This is the handle that the
     shared memory provider supplied at the 
     <i>pSharedMemoryProviderContext</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">
     NetAllocateSharedMemory</a> function.


## -remarks



NDIS calls the 
    <i>NetFreeSharedMemory</i> function of a shared memory provider when a driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreesharedmemory">NdisFreeSharedMemory</a> function.

The shared memory provider specified the entry point (FREE_SHARED_MEMORY_HANDLER) for 
    <i>NetFreeSharedMemory</i> in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_provider_characteristics">
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_provider_characteristics">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreesharedmemory">NdisFreeSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">NetAllocateSharedMemory</a>
 

 

