---
UID: NF:nblapi.NdisFreeNetBufferListPool
title: NdisFreeNetBufferListPool
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeNetBufferListPool function to free a NET_BUFFER_LIST structure pool.
tech.root: netvista 
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: Ndis.sys
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql:  <= DISPATCH_LEVEL
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
 - DllExport
api_location:
 - nblapi.h
api_name:
 - NdisFreeNetBufferListPool
f1_keywords:
 - NdisFreeNetBufferListPool
 - nblapi/NdisFreeNetBufferListPool
dev_langs:
 - c++
---

# NdisFreeNetBufferListPool function


## -description

Call the 
  <b>NdisFreeNetBufferListPool</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure pool.

## -parameters

### -param PoolHandle 

[in]
A handle that was obtained from a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function.

## -remarks

Before freeing a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure pool, you must
    free all the NET_BUFFER_LIST structures in the pool. To free a NET_BUFFER_LIST structure, call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbufferlist">NdisFreeNetBufferList</a>

