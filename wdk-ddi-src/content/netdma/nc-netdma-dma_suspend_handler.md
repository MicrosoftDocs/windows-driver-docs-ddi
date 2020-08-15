---
UID: NC:netdma.DMA_SUSPEND_HANDLER
title: DMA_SUSPEND_HANDLER (netdma.h)
description: The ProviderSuspendDma function suspends the DMA transfers that are currently in progress on a DMA channel.
old-location: netvista\providersuspenddma.htm
tech.root: netvista
ms.assetid: b020b0c6-eb69-44d0-a374-b39eb2f536f1
ms.date: 05/02/2018
keywords: ["DMA_SUSPEND_HANDLER callback function"]
ms.keywords: DMA_SUSPEND_HANDLER, DMA_SUSPEND_HANDLER callback, ProviderSuspendDma, ProviderSuspendDma callback function [Network Drivers Starting with Windows Vista], netdma/ProviderSuspendDma, netdma_ref_f194d9b0-083c-46a1-9e39-aa33c62af512.xml, netvista.providersuspenddma
f1_keywords:
 - "netdma/ProviderSuspendDma"
 - "ProviderSuspendDma"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- netdma.h
api_name:
- ProviderSuspendDma
targetos: Windows
req.typenames: 
---

# DMA_SUSPEND_HANDLER callback function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderSuspendDma</i> function suspends the DMA transfers that are currently in progress on a DMA
  channel.


## -parameters




### -param ProviderChannelContext 
[in]
A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">
     ProviderAllocateDmaChannel</a> function.


### -param pLastDescriptor 
[out]
A pointer to a variable that contains the physical address of the last successfully processed DMA
     descriptor. The DMA provider provides this address before returning from 
     <i>ProviderSuspendDma</i>.


## -returns



<i>ProviderSuspendDma</i> returns one of the following status values:

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
    <i>ProviderSuspendDma</i> function is an optional function for NetDMA providers. The NetDMA interface can
    call the 
    <i>ProviderSuspendDma</i> function, if any, to temporarily suspend any DMA transfers that are in progress
    on a DMA channel.

The DMA provider completes the transfer of the current DMA descriptor before it returns from 
    <i>ProviderSuspendDma</i>. If completion status reporting is enabled, the DMA engine writes the 
    <b>NetDmaTransferStatusSuspend</b> status in the address that is specified in the 
    <b>CompletionVirtualAddress</b> and 
    <b>CompletionPhysicalAddress</b> members in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_parameters">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

While the DMA transfers are suspended, the NetDMA interface can modify the DMA descriptor linked list
    (for example, to insert or delete descriptors).

The NetDMA interface calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_resume_handler">ProviderResumeDma</a> function to resume DMA
    operations that were suspended by calling 
    <i>ProviderSuspendDma</i>.

NetDMA calls 
    <i>ProviderSuspendDma</i> at IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_parameters">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_resume_handler">ProviderResumeDma</a>
 

 

