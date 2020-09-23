---
UID: NC:netdma.DMA_RESET_HANDLER
title: DMA_RESET_HANDLER (netdma.h)
description: The ProviderResetChannel function resets a DMA channel to the initial state that existed after the DMA channel was allocated.
old-location: netvista\providerresetchannel.htm
tech.root: netvista
ms.assetid: ee882897-fbc6-4017-8c30-2a54f6c49491
ms.date: 05/02/2018
keywords: ["DMA_RESET_HANDLER callback function"]
ms.keywords: DMA_RESET_HANDLER, DMA_RESET_HANDLER callback, ProviderResetChannel, ProviderResetChannel callback function [Network Drivers Starting with Windows Vista], netdma/ProviderResetChannel, netdma_ref_b8d39a6d-73fa-4d8b-b7c7-3f5eb47a4fc4.xml, netvista.providerresetchannel
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DMA_RESET_HANDLER
 - netdma/DMA_RESET_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - netdma.h
api_name:
 - ProviderResetChannel
---

# DMA_RESET_HANDLER callback function


## -description

<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderResetChannel</i> function resets a DMA channel to the initial state that existed after the DMA
  channel was allocated.

## -parameters

### -param ProviderChannelContext 

[in]
A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">
     ProviderAllocateDmaChannel</a> function.

## -returns

<i>ProviderResetChannel</i> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed for unspecified reasons.

</td>
</tr>
</table>

## -remarks

The 
    <i>ProviderResetChannel</i> function is an optional function for NetDMA providers. The NetDMA interface
    calls the DMA provider driver's 
    <i>ProviderResetChannel</i> function, if any, to reset a DMA channel.

In 
    <i>ProviderResetChannel</i>, the NetDMA provider should terminate any active transfer immediately without
    completing the transfer of the data that is associated with the current DMA descriptor. If completion status reporting is enabled, the DMA engine writes the 
    <b>NetDmaTransferStatusHalted</b> status in the address that is specified in the 
    <b>CompletionVirtualAddress</b> and 
    <b>CompletionPhysicalAddress</b> members in the 
    <a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_parameters">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

After the reset operation is complete, the DMA channel must be in the initial state that existed after
    the channel was allocated. After the NetDMA interface calls 
    <i>ProviderResetChannel</i>, the DMA provider cannot access any of the previously submitted DMA
    descriptors. The DMA channel must be ready for the NetDMA interface to call the 
    <a href="/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_start_handler">ProviderStartDma</a> function.

NetDMA calls 
    <i>ProviderResetChannel</i> at IRQL <= DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_parameters">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a>



<a href="/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_start_handler">ProviderStartDma</a>