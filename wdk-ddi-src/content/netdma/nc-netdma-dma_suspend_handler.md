---
UID: NC:netdma.DMA_SUSPEND_HANDLER
title: DMA_SUSPEND_HANDLER
author: windows-driver-content
description: The ProviderSuspendDma function suspends the DMA transfers that are currently in progress on a DMA channel.
old-location: netvista\providersuspenddma.htm
old-project: netvista
ms.assetid: b020b0c6-eb69-44d0-a374-b39eb2f536f1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _MIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProviderSuspendDma
req.alt-loc: netdma.h
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
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_SUSPEND_HANDLER callback



## -description

## -prototype

````
DMA_SUSPEND_HANDLER ProviderSuspendDma;

NTSTATUS ProviderSuspendDma(
  _In_  PVOID             ProviderChannelContext,
  _Out_ PPHYSICAL_ADDRESS *pLastDescriptor
)
{ ... }
````


## -parameters

### -param ProviderChannelContext [in]

A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">
     ProviderAllocateDmaChannel</a> function.


### -param pLastDescriptor [out]

A pointer to a variable that contains the physical address of the last successfully processed DMA
     descriptor. The DMA provider provides this address before returning from 
     <i>ProviderSuspendDma</i>.


## -returns
<i>ProviderSuspendDma</i> returns one of the following status values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The operation failed for unspecified reasons.

 


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
    <a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

While the DMA transfers are suspended, the NetDMA interface can modify the DMA descriptor linked list
    (for example, to insert or delete descriptors).

The NetDMA interface calls the 
    <a href="..\netdma\nc-netdma-dma_resume_handler.md">ProviderResumeDma</a> function to resume DMA
    operations that were suspended by calling 
    <i>ProviderSuspendDma</i>.

NetDMA calls 
    <i>ProviderSuspendDma</i> at IRQL &lt;= DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">NET_DMA_CHANNEL_PARAMETERS</a>
</dt>
<dt>
<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>
</dt>
<dt>
<a href="..\netdma\nc-netdma-dma_resume_handler.md">ProviderResumeDma</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_SUSPEND_HANDLER callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

