---
UID: NF:nblapi.NdisAdvanceNetBufferDataStart
title: NdisAdvanceNetBufferDataStart
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisAdvanceNetBufferDataStart function to release the used data space that was added with the NdisRetreatNetBufferDataStart function.
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
 - NdisAdvanceNetBufferDataStart
f1_keywords:
 - NdisAdvanceNetBufferDataStart
 - nblapi/NdisAdvanceNetBufferDataStart
dev_langs:
 - c++
---


# NdisAdvanceNetBufferDataStart function


## -description

Call the 
  <b>NdisAdvanceNetBufferDataStart</b> function to release the 
  <i>used data space</i> that was added with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
  NdisRetreatNetBufferDataStart</a> function.

## -parameters

### -param NetBuffer 

[in]
A pointer to a previously allocated 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

### -param DataOffsetDelta 

[in]
The amount of 
     <i>used data space</i> to release. NDIS adjusts the value of the 
     <b>DataOffset</b> member of the NET_BUFFER structure accordingly.

### -param FreeMdl 

[in]
A BOOLEAN value that, if <b>TRUE</b>, requests NDIS to free any MDLs that become unused in the advance
     operation. If 
     <i>FreeMdl</i> is <b>FALSE</b>, NDIS retains unused MDLs for use in subsequent retreat operations.

### -param FreeMdlHandler 

[in, optional]
An optional entry point for an 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_free_mdl_handler">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.

## -remarks

If NDIS allocated memory to satisfy a corresponding call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
    NdisRetreatNetBufferDataStart</a> function, then 
    <b>NdisAdvanceNetBufferDataStart</b> frees the memory that 
    <b>NdisRetreatNetBufferDataStart</b> allocated. Otherwise, the memory remains in the MDL and only the
    value of the 
    <b>DataOffset</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure is modified.

NDIS calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_free_mdl_handler">NetFreeMdl</a> function specified at 
    <i>FreeMdl</i> if 
    <b>NdisAdvanceNetBufferDataStart</b> must free memory. NDIS calls 
    <i>NetFreeMdl</i> only to free the MDLs and memory that the driver allocated in the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_allocate_mdl_handler">NetAllocateMdl</a> function.

When protocol drivers call 
    <b>NdisAdvanceNetBufferDataStart</b> on the receive path to access the various transport headers, the MDL
    chain should not be modified and 
    <i>FreeMdl</i> is <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_allocate_mdl_handler">NetAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_free_mdl_handler">NetFreeMdl</a>
