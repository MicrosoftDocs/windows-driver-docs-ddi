<<<<<<< HEAD:wdk-ddi-src/content/nblapi/nf-nblapi-ndisfreenetbufferpool.md
---
UID: NF:nblapi.NdisFreeNetBufferPool
title: NdisFreeNetBufferPool
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisFreeNetBufferPool function to free NET_BUFFER structure pools that are created with the NdisAllocateNetBufferPool function.
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
 - NdisFreeNetBufferPool
f1_keywords:
 - NdisFreeNetBufferPool
 - nblapi/NdisFreeNetBufferPool
dev_langs:
 - c++
---

# NdisFreeNetBufferPool function


## -description

Call the 
  <b>NdisFreeNetBufferPool</b> function to free 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pools that are created with
  the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
  NdisAllocateNetBufferPool</a> function.

## -parameters

### -param PoolHandle 

[in]
The pool handle for the NET_BUFFER structure pool to be freed.

## -remarks

You should free all the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures in a pool before freeing
    the NET_BUFFER structure pool. Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a> function to free each
    NET_BUFFER structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a>

=======
---
UID: NF:ndis.NdisFreeNetBufferPool
title: NdisFreeNetBufferPool function (ndis.h)
description: Call the NdisFreeNetBufferPool function to free NET_BUFFER structure pools that are created with the NdisAllocateNetBufferPool function.
old-location: netvista\ndisfreenetbufferpool.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeNetBufferPool function"]
ms.keywords: NdisFreeNetBufferPool, NdisFreeNetBufferPool function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferPool, ndis_netbuf_functions_ref_8fcb5f46-efc3-4059-9774-cbdf14c5500a.xml, netvista.ndisfreenetbufferpool
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFreeNetBufferPool
 - ndis/NdisFreeNetBufferPool
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeNetBufferPool
---

# NdisFreeNetBufferPool function


## -description

Call the 
  <b>NdisFreeNetBufferPool</b> function to free 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pools that are created with
  the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
  NdisAllocateNetBufferPool</a> function.

## -parameters

### -param PoolHandle 

[in]
The pool handle for the NET_BUFFER structure pool to be freed.

## -remarks

You should free all the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures in a pool before freeing
    the NET_BUFFER structure pool. Call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a> function to free each
    NET_BUFFER structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a>
>>>>>>> release-iron:wdk-ddi-src/content/ndis/nf-ndis-ndisfreenetbufferpool.md
