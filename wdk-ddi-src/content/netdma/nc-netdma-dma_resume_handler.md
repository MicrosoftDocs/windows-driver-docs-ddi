---
UID: NC:netdma.DMA_RESUME_HANDLER
title: DMA_RESUME_HANDLER
author: windows-driver-content
description: The ProviderResumeDma function resumes the DMA transfers that are currently suspended on a DMA channel.
old-location: netvista\providerresumedma.htm
tech.root: netvista
ms.assetid: 06609603-eeed-4fb0-a878-87cad2e72b46
ms.date: 05/02/2018
ms.keywords: DMA_RESUME_HANDLER, DMA_RESUME_HANDLER callback, ProviderResumeDma, ProviderResumeDma callback function [Network Drivers Starting with Windows Vista], netdma/ProviderResumeDma, netdma_ref_75548093-1640-40f2-a715-0918b92900d3.xml, netvista.providerresumedma
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
-	ProviderResumeDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# DMA_RESUME_HANDLER callback function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderResumeDma</i> function resumes the DMA transfers that are currently suspended on a DMA
  channel.


## -parameters




### -param ProviderChannelContext [in]

A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">
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
    <a href="https://msdn.microsoft.com/b020b0c6-eb69-44d0-a374-b39eb2f536f1">ProviderSuspendDma</a> function. If the DMA
    provider driver specifies an entry point for a 
    <i>ProviderSuspendDma</i> function, it must also specify an entry point for a 
    <i>ProviderResumeDma</i> function.

When the DMA engine resumes transfers, the hardware should reload the DMA descriptor that it processed
    last to get the new next descriptor.

NetDMA calls 
    <i>ProviderResumeDma</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">ProviderAllocateDmaChannel</a>



<a href="https://msdn.microsoft.com/b020b0c6-eb69-44d0-a374-b39eb2f536f1">ProviderSuspendDma</a>
 

 

