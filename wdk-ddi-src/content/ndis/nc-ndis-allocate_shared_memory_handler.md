---
UID: NC:ndis.ALLOCATE_SHARED_MEMORY_HANDLER
title: ALLOCATE_SHARED_MEMORY_HANDLER
author: windows-driver-content
description: The NetAllocateSharedMemory function (ALLOCATE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver allocates shared memory from a shared memory provider.
old-location: netvista\netallocatesharedmemory.htm
old-project: netvista
ms.assetid: d85b4f28-707b-4525-afd8-83e1ceb2674e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.netallocatesharedmemory, NetAllocateSharedMemory callback function [Network Drivers Starting with Windows Vista], NetAllocateSharedMemory, ALLOCATE_SHARED_MEMORY_HANDLER, ALLOCATE_SHARED_MEMORY_HANDLER, ndis/NetAllocateSharedMemory, ndis_shared_memory_ref_8830fb4b-2e73-4994-91c6-a885d1c0ef74.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Ndis.h
apiname: 
-	NetAllocateSharedMemory
product: Windows
targetos: Windows
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
     <mshelp:link keywords="netvista.ndis_shared_memory_provider_characteristics" tabindex="0"><b>
     NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</b></mshelp:link> structure.


### -param SharedMemoryParameters [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_shared_memory_parameters" tabindex="0"><b>
     NDIS_SHARED_MEMORY_PARAMETERS</b></mshelp:link> structure that defines the requested attributes for the shared
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
    <mshelp:link keywords="netvista.ndisallocatesharedmemory" tabindex="0"><b>
    NdisAllocateSharedMemory</b></mshelp:link> function.

The shared memory provider specified the entry point (ALLOCATE_SHARED_MEMORY_HANDLER) for 
    <i>NetAllocateSharedMemory</i> in the 
    <mshelp:link keywords="netvista.ndis_shared_memory_provider_characteristics" tabindex="0"><b>
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</b></mshelp:link> structure.



## -see-also

<a href="..\ndis\nf-ndis-ndisallocatesharedmemory.md">NdisAllocateSharedMemory</a>

<a href="..\ndis\ns-ndis-_ndis_shared_memory_parameters.md">NDIS_SHARED_MEMORY_PARAMETERS</a>

<mshelp:link keywords="netvista.ndis_shared_memory_provider_characteristics" tabindex="0"><b>
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20ALLOCATE_SHARED_MEMORY_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

