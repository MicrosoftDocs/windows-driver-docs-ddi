---
UID: NF:ndis.NdisAllocateNetBufferMdlAndData
title: NdisAllocateNetBufferMdlAndData function (ndis.h)
description: NDIS drivers call the NdisAllocateNetBufferMdlAndData function to allocate a NET_BUFFER structure along with the associated MDL and data.
old-location: netvista\ndisallocatenetbuffermdlanddata.htm
tech.root: netvista
ms.assetid: cfac9061-a685-4e67-aaa2-ca43b7e36cfa
ms.date: 05/02/2018
keywords: ["NdisAllocateNetBufferMdlAndData function"]
ms.keywords: NdisAllocateNetBufferMdlAndData, NdisAllocateNetBufferMdlAndData function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferMdlAndData, ndis_netbuf_functions_ref_4f5d872d-11c1-4d75-889c-0c2157ce5f2e.xml, netvista.ndisallocatenetbuffermdlanddata
f1_keywords:
 - "ndis/NdisAllocateNetBufferMdlAndData"
 - "NdisAllocateNetBufferMdlAndData"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateNetBufferMdlAndData
targetos: Windows
req.typenames: 
---

# NdisAllocateNetBufferMdlAndData function


## -description


NDIS drivers call the 
  <b>NdisAllocateNetBufferMdlAndData</b> function to allocate a NET_BUFFER structure along with the associated
  MDL and data.


## -parameters




### -param PoolHandle 
[in]
A NET_BUFFER structure pool handle that was previously returned from a call to the 
     <b>NdisAllocateNetBufferPool</b> function.


## -returns



<b>NdisAllocateNetBufferMdlAndData</b> returns a pointer to the NET_BUFFER structure that NDIS allocated.
     If the allocation was unsuccessful, this pointer is <b>NULL</b>.




## -remarks



The caller must call the 
    <b>NdisAllocateNetBufferPool</b> function and specify the maximum size of the data buffers. Given this
    value, NDIS can preallocate buffers for the caller.

This function allocates a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure, MDL and data in a single
    memory buffer. This is useful to achieve high performance when NET_BUFFER structures are frequently
    allocated and freed. The caller should not call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a> to allocate
    NET_BUFFERs out of NET_BUFFER pools which contain data.

NDIS uses the 
    <i>PoolHandle</i> parameter to get a block of memory, and then creates the NET_BUFFER, MDL, and data
    buffer.

To free the NET_BUFFER and associated information, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a>
 

 

