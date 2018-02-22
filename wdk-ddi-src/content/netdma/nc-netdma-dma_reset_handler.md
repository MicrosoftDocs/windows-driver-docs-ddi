---
UID: NC:netdma.DMA_RESET_HANDLER
title: DMA_RESET_HANDLER
author: windows-driver-content
description: The ProviderResetChannel function resets a DMA channel to the initial state that existed after the DMA channel was allocated.
old-location: netvista\providerresetchannel.htm
old-project: netvista
ms.assetid: ee882897-fbc6-4017-8c30-2a54f6c49491
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.providerresetchannel, ProviderResetChannel callback function [Network Drivers Starting with Windows Vista], ProviderResetChannel, DMA_RESET_HANDLER, DMA_RESET_HANDLER, netdma/ProviderResetChannel, netdma_ref_b8d39a6d-73fa-4d8b-b7c7-3f5eb47a4fc4.xml
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
-	ProviderResetChannel
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_RESET_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderResetChannel</i> function resets a DMA channel to the initial state that existed after the DMA
  channel was allocated.


## -prototype


````
DMA_RESET_HANDLER ProviderResetChannel;

NTSTATUS ProviderResetChannel(
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
    <a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

After the reset operation is complete, the DMA channel must be in the initial state that existed after
    the channel was allocated. After the NetDMA interface calls 
    <i>ProviderResetChannel</i>, the DMA provider cannot access any of the previously submitted DMA
    descriptors. The DMA channel must be ready for the NetDMA interface to call the 
    <a href="..\netdma\nc-netdma-dma_start_handler.md">ProviderStartDma</a> function.

NetDMA calls 
    <i>ProviderResetChannel</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netdma\nc-netdma-dma_start_handler.md">ProviderStartDma</a>



<a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_RESET_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

