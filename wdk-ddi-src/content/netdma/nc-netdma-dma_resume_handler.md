---
UID: NC:netdma.DMA_RESUME_HANDLER
title: DMA_RESUME_HANDLER
author: windows-driver-content
description: The ProviderResumeDma function resumes the DMA transfers that are currently suspended on a DMA channel.
old-location: netvista\providerresumedma.htm
old-project: netvista
ms.assetid: 06609603-eeed-4fb0-a878-87cad2e72b46
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DMA_RESUME_HANDLER, ProviderResumeDma, ProviderResumeDma callback function [Network Drivers Starting with Windows Vista], netdma/ProviderResumeDma, netdma_ref_75548093-1640-40f2-a715-0918b92900d3.xml, netvista.providerresumedma
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
-	ProviderResumeDma
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_RESUME_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderResumeDma</i> function resumes the DMA transfers that are currently suspended on a DMA
  channel.


## -prototype


````
DMA_RESUME_HANDLER ProviderResumeDma;

NTSTATUS ProviderResumeDma(
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



<i>ProviderResumeDma</i> returns one of the following status values:

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
    <i>ProviderSuspendDma</i> function is an optional function for NetDMA providers. The NetDMA interface
    calls the 
    <i>ProviderResumeDma</i> function, if any, to resume DMA operations that were suspended by calling the 
    <a href="..\netdma\nc-netdma-dma_suspend_handler.md">ProviderSuspendDma</a> function. If the DMA
    provider driver specifies an entry point for a 
    <i>ProviderSuspendDma</i> function, it must also specify an entry point for a 
    <i>ProviderResumeDma</i> function.

When the DMA engine resumes transfers, the hardware should reload the DMA descriptor that it processed
    last to get the new next descriptor.

NetDMA calls 
    <i>ProviderResumeDma</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>



<a href="..\netdma\nc-netdma-dma_suspend_handler.md">ProviderSuspendDma</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_RESUME_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

