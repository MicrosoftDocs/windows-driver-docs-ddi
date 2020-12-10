---
UID: NF:nblapi.NdisAdvanceNetBufferListDataStart
title: NdisAdvanceNetBufferListDataStart
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAdvanceNetBufferListDataStart function to release data space that was claimed in previous calls to the NdisRetreatNetBufferListDataStart function.
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
 - NdisAdvanceNetBufferListDataStart
f1_keywords:
 - NdisAdvanceNetBufferListDataStart
 - nblapi/NdisAdvanceNetBufferListDataStart
dev_langs:
 - c++
---

# NdisAdvanceNetBufferListDataStart function


## -description

Call the 
  <b>NdisAdvanceNetBufferListDataStart</b> function to release data space that was claimed in previous calls
  to the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
  NdisRetreatNetBufferListDataStart</a> function.

## -parameters

### -param NetBufferList 

[in]
A pointer to a previously allocated 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

### -param DataOffsetDelta 

[in]
The amount of 
     <i>used data space</i> to release.

### -param FreeMdl 

[in]
If <b>TRUE</b> and NDIS allocated memory to satisfy the corresponding 
     <b>NdisRetreatNetBufferListDataStart</b> call, this function frees the memory that was allocated and the
     associated MDL.

### -param FreeMdlMdlHandler

An optional entry point for an 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_free_mdl_handler">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.

## -remarks

<b>NdisAdvanceNetBufferListDataStart</b> releases 
    <i>used data space</i> for all the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures in a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure. If 
    <i>FreeMdl</i> is <b>TRUE</b> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
    NdisRetreatNetBufferListDataStart</a> allocated memory to satisfy the corresponding allocation request,    
    <b>NdisAdvanceNetBufferListDataStart</b> frees the allocated memory. Calling this function is equivalent
    to calling 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
    NdisAdvanceNetBufferDataStart</a> for every NET_BUFFER structure on the NET_BUFFER_LIST structure.
    However, calling 
    <b>NdisAdvanceNetBufferListDataStart</b> is more efficient.

When protocol drivers call 
    <b>NdisAdvanceNetBufferListDataStart</b> on the receive path to access the various transport headers, the
    MDL chain should not be modified and 
    <i>FreeMdl</i> is <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferlistdatastart">
   NdisRetreatNetBufferListDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_allocate_mdl_handler">NetAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_free_mdl_handler">NetFreeMdl</a>
