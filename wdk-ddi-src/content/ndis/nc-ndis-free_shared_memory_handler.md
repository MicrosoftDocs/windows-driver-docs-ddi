---
UID: NC:ndis.FREE_SHARED_MEMORY_HANDLER
title: FREE_SHARED_MEMORY_HANDLER
author: windows-driver-content
description: The NetFreeSharedMemory function (FREE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver frees shared memory from a shared memory provider.
old-location: netvista\netfreesharedmemory.htm
old-project: netvista
ms.assetid: fdc3dfe7-6980-493d-ad41-aed501db3a6b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FREE_SHARED_MEMORY_HANDLER, NetFreeSharedMemory, NetFreeSharedMemory callback function [Network Drivers Starting with Windows Vista], ndis/NetFreeSharedMemory, ndis_shared_memory_ref_15b5aca1-e5be-4063-812f-9d98a4e72cd4.xml, netvista.netfreesharedmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	NetFreeSharedMemory
product:
- Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FREE_SHARED_MEMORY_HANDLER callback


## -description


The 
  <i>NetFreeSharedMemory</i> function (FREE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver
  frees shared memory from a shared memory provider.


## -parameters




### -param ProviderContext [in]

An NDIS_HANDLE to a block of driver-allocated context information that identifies the provider.
     The provider supplied this information in the 
     <b>ProviderContext</b> member of the 
     <a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
     NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.


### -param SharedMemoryProviderContext [in]

A handle for a context area that identifies the shared memory block. This is the handle that the
     shared memory provider supplied at the 
     <i>pSharedMemoryProviderContext</i> parameter of the 
     <a href="https://msdn.microsoft.com/d85b4f28-707b-4525-afd8-83e1ceb2674e">
     NetAllocateSharedMemory</a> function.


## -returns



None




## -remarks



NDIS calls the 
    <i>NetFreeSharedMemory</i> function of a shared memory provider when a driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562601">NdisFreeSharedMemory</a> function.

The shared memory provider specified the entry point (FREE_SHARED_MEMORY_HANDLER) for 
    <i>NetFreeSharedMemory</i> in the 
    <a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/45001da1-5fe3-4383-8da7-31e3ee115c1f">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562601">NdisFreeSharedMemory</a>



<a href="https://msdn.microsoft.com/d85b4f28-707b-4525-afd8-83e1ceb2674e">NetAllocateSharedMemory</a>
 

 

