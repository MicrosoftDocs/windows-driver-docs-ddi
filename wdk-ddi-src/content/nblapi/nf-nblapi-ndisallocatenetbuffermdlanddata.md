---
UID: NF:nblapi.NdisAllocateNetBufferMdlAndData
title: NdisAllocateNetBufferMdlAndData
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: NDIS drivers call the NdisAllocateNetBufferMdlAndData function to allocate a NET_BUFFER structure along with the associated MDL and data.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: 
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - nblapi.h
api_name:
 - NdisAllocateNetBufferMdlAndData
f1_keywords:
 - NdisAllocateNetBufferMdlAndData
 - nblapi/NdisAllocateNetBufferMdlAndData
dev_langs:
 - c++
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
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure, MDL and data in a single
    memory buffer. This is useful to achieve high performance when NET_BUFFER structures are frequently
    allocated and freed. The caller should not call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a> to allocate
    NET_BUFFERs out of NET_BUFFER pools which contain data.

NDIS uses the 
    <i>PoolHandle</i> parameter to get a block of memory, and then creates the NET_BUFFER, MDL, and data
    buffer.

To free the NET_BUFFER and associated information, call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a>
