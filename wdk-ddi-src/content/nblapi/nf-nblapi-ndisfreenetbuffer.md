---
UID: NF:nblapi.NdisFreeNetBuffer
title: NdisFreeNetBuffer
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeNetBuffer function to free a NET_BUFFER structure that was previously allocated from a NET_BUFFER structure pool with the NdisAllocateNetBuffer function.
tech.root: netvista 
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateNetBuffer
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
 - NdisFreeNetBuffer
f1_keywords:
 - NdisFreeNetBuffer
 - nblapi/NdisFreeNetBuffer
dev_langs:
 - c++
---

# NdisFreeNetBuffer function


## -description

Call the 
  <b>NdisFreeNetBuffer</b> function to free a 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure that was previously allocated
  from a NET_BUFFER structure pool with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a> function.

## -parameters

### -param NetBuffer 

[in]
A pointer to a NET_BUFFER structure that was allocated by calling 
     <b>NdisAllocateNetBuffer</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>

