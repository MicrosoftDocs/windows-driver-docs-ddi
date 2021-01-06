---
UID: NF:ndis.NdisMFreeNetBufferSGList
title: NdisMFreeNetBufferSGList function (ndis.h)
description: Bus-master miniport drivers call the NdisMFreeNetBufferSGList function to free scatter/gather list resources that were allocated by calling the NdisMAllocateNetBufferSGList function.
old-location: netvista\ndismfreenetbuffersglist.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMFreeNetBufferSGList function"]
ms.keywords: NdisMFreeNetBufferSGList, NdisMFreeNetBufferSGList function [Network Drivers Starting with Windows Vista], ndis/NdisMFreeNetBufferSGList, ndis_sgdma_ref_e2f486cf-eba4-410d-ac18-724efb32fd59.xml, netvista.ndismfreenetbuffersglist
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMFreeNetBufferSGList
 - ndis/NdisMFreeNetBufferSGList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMFreeNetBufferSGList
---

# NdisMFreeNetBufferSGList function


## -description

> [!CAUTION]
> For ARM and ARM64 processors, we strongly recommend that NDIS driver writers use WDF DMA or WDM DMA instead of NDIS Scatter/Gather DMA. 
>
> For more information about WDF DMA, see [Handling DMA Operations in KMDF Drivers](/windows-hardware/drivers/wdf/handling-dma-operations-in-kmdf-drivers).
>
> For more information about WDM DMA, see the DMA-related child topics of [Managing Input/Output for Drivers](/windows-hardware/drivers/kernel/managing-input-output-for-drivers).

Bus-master miniport drivers call the 
  <b>NdisMFreeNetBufferSGList</b> function to free scatter/gather list resources that were allocated by
  calling the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatenetbuffersglist">
  NdisMAllocateNetBufferSGList</a> function.

## -parameters

### -param NdisMiniportDmaHandle 

[in]
A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
     NdisMRegisterScatterGatherDma</a> function.

### -param pSGL 

[in]
A pointer to a miniport driver scatter/gather list buffer.

### -param NetBuffer 

[in]
A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure associated with the
     specified scatter/gather list buffer.

## -remarks

Bus-master miniport drivers must call the 
    <b>NdisMFreeNetBufferSGList</b> function to free a scatter/gather list. A miniport driver typically calls 
    <b>NdisMFreeNetBufferSGList</b> from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a> function
    while it is handling a send complete interrupt or at any time that the driver no longer requires the
    scatter/gather list. Do not call 
    <b>NdisMFreeNetBufferSGList</b> while the driver or hardware is still accessing the memory that is
    described by the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure that is associated with the
    scatter/gather list.

Miniport drivers can free the buffer that was specified in the 
    <i>ScatterGatherListBuffer</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a> function after 
    <b>NdisMFreeNetBufferSGList</b> returns.

Before accessing received data, miniport drivers must call <b>NdisMFreeNetBufferSGList</b> to flush the memory cache.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/network/ndis-scatter-gather-dma">NDIS Scatter/Gather DMA</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>
