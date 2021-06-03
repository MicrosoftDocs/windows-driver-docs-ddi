---
UID: NC:nblapi.NET_BUFFER_FREE_MDL
tech.root: netvista
title: NET_BUFFER_FREE_MDL
ms.date: 06/15/2021
ms.topic: language-reference
targetos: Windows
description: The NetFreeMdl function frees an MDL that was previously allocated by the NetAllocateMdl function.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: 
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
 - NET_BUFFER_FREE_MDL
f1_keywords:
 - NET_BUFFER_FREE_MDL
 - nblapi/NET_BUFFER_FREE_MDL
dev_langs:
 - c++
---

## -description

The 
  <i>NetFreeMdl</i> function frees an MDL that was previously allocated by the 
  <a href="/windows-hardware/drivers/ddi/nblapi/nc-nblapi-net_buffer_allocate_mdl">NetAllocateMdl</a> function.

## -parameters

### -param Mdl 

[in]
A pointer to the MDL that is to be freed.

## -remarks

If the NDIS driver specifies an entry point for the 
    <i>NetFreeMdl</i> function at the 
    <i>FreeMdl</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
    NdisAdvanceNetBufferDataStart</a> function, NDIS calls 
    <i>NetFreeMdl</i> to free an MDL and memory.

<i>NetFreeMdl</i> frees the MDL and memory that were allocated by the 
    <a href="/windows-hardware/drivers/ddi/nblapi/nc-nblapi-net_buffer_allocate_mdl">NetAllocateMdl</a> function.

When 
    <i>NetFreeMdl</i> frees the memory, it should use the same memory management mechanism that was used in 
    <i>NetAllocateMdl</i> to allocate the memory.

NDIS calls 
    <i>NetFreeMdl</i> at IRQL <= DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/nblapi/nc-nblapi-net_buffer_allocate_mdl">NetAllocateMdl</a>

