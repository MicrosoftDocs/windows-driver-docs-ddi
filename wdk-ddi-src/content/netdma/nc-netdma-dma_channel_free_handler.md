---
UID: NC:netdma.DMA_CHANNEL_FREE_HANDLER
title: DMA_CHANNEL_FREE_HANDLER (netdma.h)
description: The ProviderFreeDmaChannel function frees a DMA channel that the ProviderAllocateDmaChannel function previously allocated.
old-location: netvista\providerfreedmachannel.htm
tech.root: netvista
ms.assetid: 5bbe432d-f236-46ec-8e78-788bd676b852
ms.date: 05/02/2018
ms.keywords: DMA_CHANNEL_FREE_HANDLER, DMA_CHANNEL_FREE_HANDLER callback, ProviderFreeDmaChannel, ProviderFreeDmaChannel callback function [Network Drivers Starting with Windows Vista], netdma/ProviderFreeDmaChannel, netdma_ref_d81eae9f-e306-4ac7-a4ce-3e4831b45c39.xml, netvista.providerfreedmachannel
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- netdma.h
api_name:
- ProviderFreeDmaChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# DMA_CHANNEL_FREE_HANDLER callback function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderFreeDmaChannel</i> function frees a DMA channel that the 
  <a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">
  ProviderAllocateDmaChannel</a> function previously allocated.


## -parameters




### -param ProviderChannelContext [in]

A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">
     ProviderAllocateDmaChannel</a> function.


## -returns



None




## -remarks



The NetDMA interface calls a DMA provider driver's 
    <i>ProviderFreeDmaChannel</i> function to free a DMA channel. Before the NetDMA interface calls 
    <i>ProviderFreeDmaChannel</i>, it ensures that there are no outstanding DMA operations on this
    channel.

After the NetDMA interface calls 
    <i>ProviderFreeDmaChannel</i>, it does not call any 
    <i>ProviderXxx</i> functions for the freed channel.

The NetDMA interface frees all of the allocated DMA channels before it returns from the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568335">NetDmaProviderStop</a> function.

NetDMA calls 
    <i>ProviderFreeDmaChannel</i> at IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568335">NetDmaProviderStop</a>



<a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">ProviderAllocateDmaChannel</a>
 

 

