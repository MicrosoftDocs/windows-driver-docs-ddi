---
UID: NC:netdma.DMA_ABORT_HANDLER
title: DMA_ABORT_HANDLER
author: windows-driver-content
description: The ProviderAbortDma function cancels any DMA transfers that are associated with a DMA channel.
old-location: netvista\providerabortdma.htm
old-project: netvista
ms.assetid: b9c23f36-0885-49fd-b92e-dac38d5f363f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.providerabortdma, ProviderAbortDma callback function [Network Drivers Starting with Windows Vista], ProviderAbortDma, DMA_ABORT_HANDLER, DMA_ABORT_HANDLER, netdma/ProviderAbortDma, netdma_ref_b030a880-2a65-4fef-9f91-4a4bc4fa17b5.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	netdma.h
apiname:
-	ProviderAbortDma
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_ABORT_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderAbortDma</i> function cancels any DMA transfers that are associated with a DMA channel.


## -prototype


````
DMA_ABORT_HANDLER ProviderAbortDma;

NTSTATUS ProviderAbortDma(
  _In_ PVOID ProviderChannelContext
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


## -returns



<i>ProviderAbortDma</i> returns one of the following status values:

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
    <i>ProviderAbortDma</i> function is an optional function for NetDMA providers. The NetDMA interface can
    call a DMA provider driver's 
    <i>ProviderAbortDma</i> function, if any, to abort all DMA transfers that have been scheduled on a DMA
    channel.

In 
    <i>ProviderAbortDma</i>, the DMA provider should terminate the transfer immediately without completing
    the transfer of the data that is associated with the current DMA descriptor. If completion status reporting is enabled, the DMA engine writes the 
    <b>NetDmaTransferStatusHalted</b> status in the address that is specified in the 
    <b>CompletionVirtualAddress</b> and 
    <b>CompletionPhysicalAddress</b> members in the 
    <a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

After the abort operation completes, the DMA channel must be ready for the NetDMA interface to call
    the 
    <a href="..\netdma\nc-netdma-dma_start_handler.md">ProviderStartDma</a> function. The NetDMA
    interface will not call the 
    <a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a> function until after
    the transfer is restarted.

NetDMA calls 
    <i>ProviderAbortDma</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netdma\nc-netdma-dma_start_handler.md">ProviderStartDma</a>



<a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a>



<a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_ABORT_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

