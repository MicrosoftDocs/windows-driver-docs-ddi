---
UID: NC:netdma.DMA_SUSPEND_HANDLER
title: DMA_SUSPEND_HANDLER
author: windows-driver-content
description: The ProviderSuspendDma function suspends the DMA transfers that are currently in progress on a DMA channel.
old-location: netvista\providersuspenddma.htm
old-project: netvista
ms.assetid: b020b0c6-eb69-44d0-a374-b39eb2f536f1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DMA_SUSPEND_HANDLER, ProviderSuspendDma, ProviderSuspendDma callback function [Network Drivers Starting with Windows Vista], netdma/ProviderSuspendDma, netdma_ref_f194d9b0-083c-46a1-9e39-aa33c62af512.xml, netvista.providersuspenddma
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	netdma.h
api_name:
-	ProviderSuspendDma
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_SUSPEND_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderSuspendDma</i> function suspends the DMA transfers that are currently in progress on a DMA
  channel.


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


### -param *pLastDescriptor [out]

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

<a href="..\netdma\nc-netdma-dma_resume_handler.md">ProviderResumeDma</a>



<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>



<a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">NET_DMA_CHANNEL_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_SUSPEND_HANDLER callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

