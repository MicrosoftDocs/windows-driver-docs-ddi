---
UID: NS:netdma._NET_DMA_CHANNEL_CPU_AFFINITY
title: _NET_DMA_CHANNEL_CPU_AFFINITY
author: windows-driver-content
description: The NET_DMA_CHANNEL_CPU_AFFINITY structure specifies the CPU affinity of a DMA channel.
old-location: netvista\net_dma_channel_cpu_affinity.htm
old-project: netvista
ms.assetid: 660fb475-fa0a-4e04-9a91-e60422ff9292
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NET_DMA_CHANNEL_CPU_AFFINITY, NET_DMA_CHANNEL_CPU_AFFINITY, *PNET_DMA_CHANNEL_CPU_AFFINITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NET_DMA_CHANNEL_CPU_AFFINITY
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
req.irql: PASSIVE_LEVEL
req.typenames: NET_DMA_CHANNEL_CPU_AFFINITY, *PNET_DMA_CHANNEL_CPU_AFFINITY
---

# _NET_DMA_CHANNEL_CPU_AFFINITY structure



## -description

## -syntax

````
typedef struct _NET_DMA_CHANNEL_CPU_AFFINITY {
  ULONG DmaChannel;
  ULONG CpuNumber;
} NET_DMA_CHANNEL_CPU_AFFINITY, *PNET_DMA_CHANNEL_CPU_AFFINITY;
````


## -struct-fields

### -field DmaChannel

The DMA channel number. The values for this member range from zero through the maximum number of
     DMA channels that the DMA engine supports minus one. The DMA provider driver specifies the maximum
     number of DMA channels in the 
     <b>MaxDmaChannelCount</b> member of the 
     <a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
     NET_DMA_PROVIDER_CHARACTERISTICS</a> structure.


### -field CpuNumber

The target CPU that the DMA provider driver should associate with the MSI-X interrupts that are
     generated for the DMA channel that is specified in the 
     <b>DmaChannel</b> member.


## -remarks
The NetDMA interface passes an array of NET_DMA_CHANNEL_CPU_AFFINITY structures to a DMA provider
    driver's 
    <a href="..\netdma\nc-netdma-dma_channels_cpu_affinity_handler.md">
    ProviderSetDmaChannelCpuAffinity</a> function to specify the CPU affinity of the DMA channels.

The NetDMA interface calls 
    <i>ProviderSetDmaChannelCpuAffinity</i> while in the context of the 
    <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
    NetDmaRegisterProvider</a> function.


## -see-also
<dl>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>
</dt>
<dt>
<a href="..\netdma\nc-netdma-dma_channels_cpu_affinity_handler.md">
   ProviderSetDmaChannelCpuAffinity</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_DMA_CHANNEL_CPU_AFFINITY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

