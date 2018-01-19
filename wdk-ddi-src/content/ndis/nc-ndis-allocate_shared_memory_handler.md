---
UID: NC:ndis.ALLOCATE_SHARED_MEMORY_HANDLER
title: ALLOCATE_SHARED_MEMORY_HANDLER
author: windows-driver-content
description: The NetAllocateSharedMemory function (ALLOCATE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver allocates shared memory from a shared memory provider.
old-location: netvista\netallocatesharedmemory.htm
old-project: netvista
ms.assetid: d85b4f28-707b-4525-afd8-83e1ceb2674e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
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
req.alt-api: NetAllocateSharedMemory
req.alt-loc: Ndis.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# ALLOCATE_SHARED_MEMORY_HANDLER callback



## -description
The 
  <i>NetAllocateSharedMemory</i> function (ALLOCATE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when
  a driver allocates shared memory from a shared memory provider.



## -prototype

````
ALLOCATE_SHARED_MEMORY_HANDLER NetAllocateSharedMemory;

NDIS_STATUS NetAllocateSharedMemory(
  _In_    NDIS_HANDLE                    ProviderContext,
  _In_    PNDIS_SHARED_MEMORY_PARAMETERS SharedMemoryParameters,
  _Inout_ PNDIS_HANDLE                   pSharedMemoryProviderContext
)
{ ... }
````


## -parameters

### -param ProviderContext [in]

An NDIS_HANDLE to a block of driver-allocated context information that identifies the provider.
     The provider supplied this information in the 
     <b>ProviderContext</b> member of the 
     <a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
     NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.


### -param SharedMemoryParameters [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_shared_memory_parameters.md">
     NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
     memory.


### -param pSharedMemoryProviderContext [in, out]

A pointer to a handle for a shared memory context area. The shared memory provider provides a
     handle that identifies the shared memory that it allocated.


## -returns
<i>NetAllocateSharedMemory</i> can return the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The operation failed because there were insufficient resources to complete the operation.
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>The operation failed because of an invalid input parameter.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The operation failed for unspecified reasons.

 


## -remarks
NDIS calls the 
    <i>NetAllocateSharedMemory</i> function of a shared memory provider when a driver calls the 
    <a href="..\ndis\nf-ndis-ndisallocatesharedmemory.md">
    NdisAllocateSharedMemory</a> function.

The shared memory provider specified the entry point (ALLOCATE_SHARED_MEMORY_HANDLER) for 
    <i>NetAllocateSharedMemory</i> in the 
    <a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_shared_memory_parameters.md">NDIS_SHARED_MEMORY_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatesharedmemory.md">NdisAllocateSharedMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20ALLOCATE_SHARED_MEMORY_HANDLER callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

