---
UID: NC:netdma.DMA_CHANNEL_FREE_HANDLER
title: DMA_CHANNEL_FREE_HANDLER
author: windows-driver-content
description: The ProviderFreeDmaChannel function frees a DMA channel that the ProviderAllocateDmaChannel function previously allocated.
old-location: netvista\providerfreedmachannel.htm
old-project: netvista
ms.assetid: 5bbe432d-f236-46ec-8e78-788bd676b852
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.providerfreedmachannel, ProviderFreeDmaChannel callback function [Network Drivers Starting with Windows Vista], ProviderFreeDmaChannel, DMA_CHANNEL_FREE_HANDLER, DMA_CHANNEL_FREE_HANDLER, netdma/ProviderFreeDmaChannel, netdma_ref_d81eae9f-e306-4ac7-a4ce-3e4831b45c39.xml
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
-	ProviderFreeDmaChannel
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_CHANNEL_FREE_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderFreeDmaChannel</i> function frees a DMA channel that the 
  <mshelp:link keywords="netvista.providerallocatedmachannel" tabindex="0"><b>
  ProviderAllocateDmaChannel</b></mshelp:link> function previously allocated.


## -prototype


````
DMA_CHANNEL_FREE_HANDLER ProviderFreeDmaChannel;

VOID ProviderFreeDmaChannel(
  _In_ PVOID ProviderChannelContext
)
{ ... }
````


## -parameters




#### - ProviderChannelContext [in]

A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <mshelp:link keywords="netvista.providerallocatedmachannel" tabindex="0"><b>
     ProviderAllocateDmaChannel</b></mshelp:link> function.


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
    <a href="..\netdma\nf-netdma-netdmaproviderstop.md">NetDmaProviderStop</a> function.

NetDMA calls 
    <i>ProviderFreeDmaChannel</i> at IRQL &lt;= DISPATCH_LEVEL.



## -see-also

<a href="..\netdma\nf-netdma-netdmaproviderstop.md">NetDmaProviderStop</a>

<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_CHANNEL_FREE_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

