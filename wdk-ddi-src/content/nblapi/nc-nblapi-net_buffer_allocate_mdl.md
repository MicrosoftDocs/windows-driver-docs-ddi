---
UID: NC:nblapi.NET_BUFFER_ALLOCATE_MDL
tech.root: netvista
title: NET_BUFFER_ALLOCATE_MDL
ms.date: 06/15/2021
targetos: Windows
description: The NetAllocateMdl function allocates an MDL with an associated memory block of a specified size.
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
 - NET_BUFFER_ALLOCATE_MDL
f1_keywords:
 - NET_BUFFER_ALLOCATE_MDL
 - nblapi/NET_BUFFER_ALLOCATE_MDL
dev_langs:
 - c++
---

## -description

The 
  <i>NetAllocateMdl</i> function allocates an MDL with an associated memory block of a specified size.

## -parameters

### -param BufferSize 

[in]
The size of the memory block, in bytes. When calling 
     <i>NetAllocateMdl</i>, NDIS passes in the requested size.

## -returns

<i>NetAllocateMdl</i> returns a pointer to the allocated MDL. If the allocation fails, the return value
     is <b>NULL</b>.

## -remarks

If the NDIS driver specifies an entry point for the 
    <i>NetAllocateMdl</i> function at the 
    <i>AllocateMdl</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
    NdisRetreatNetBufferDataStart</a> function, NDIS calls 
    <i>NetAllocateMdl</i> to allocate an MDL and memory.

NDIS specifies the size of the associated memory block at 
    <i>BufferSize</i> .

<i>NetAllocateMdl</i> can use any allocation method that meets the driver's design requirements. When NDIS
    calls the 
    <a href="/windows-hardware/drivers/ddi/nblapi/nc-nblapi-net_buffer_free_mdl">NetFreeMdl</a> function to free the memory, the
    NDIS driver should free the memory by using the same memory management mechanism that it used to allocate
    the memory.

NDIS calls 
    <i>NetAllocateMdl</i> at IRQL <= DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/nblapi/nc-nblapi-net_buffer_free_mdl">NetFreeMdl</a>

