---
UID: NS:netdma._NET_DMA_CHANNEL_CPU_AFFINITY
title: _NET_DMA_CHANNEL_CPU_AFFINITY (netdma.h)
description: The NET_DMA_CHANNEL_CPU_AFFINITY structure specifies the CPU affinity of a DMA channel.
old-location: netvista\net_dma_channel_cpu_affinity.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NET_DMA_CHANNEL_CPU_AFFINITY structure"]
ms.keywords: "*PNET_DMA_CHANNEL_CPU_AFFINITY, NET_DMA_CHANNEL_CPU_AFFINITY, NET_DMA_CHANNEL_CPU_AFFINITY structure [Network Drivers Starting with Windows Vista], PNET_DMA_CHANNEL_CPU_AFFINITY, PNET_DMA_CHANNEL_CPU_AFFINITY structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_CHANNEL_CPU_AFFINITY, netdma/NET_DMA_CHANNEL_CPU_AFFINITY, netdma/PNET_DMA_CHANNEL_CPU_AFFINITY, netdma_ref_49129d06-9557-4441-bad7-f86b3189a287.xml, netvista.net_dma_channel_cpu_affinity"
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
req.irql: 
targetos: Windows
req.typenames: NET_DMA_CHANNEL_CPU_AFFINITY, *PNET_DMA_CHANNEL_CPU_AFFINITY
f1_keywords:
 - _NET_DMA_CHANNEL_CPU_AFFINITY
 - netdma/_NET_DMA_CHANNEL_CPU_AFFINITY
 - PNET_DMA_CHANNEL_CPU_AFFINITY
 - netdma/PNET_DMA_CHANNEL_CPU_AFFINITY
 - NET_DMA_CHANNEL_CPU_AFFINITY
 - netdma/NET_DMA_CHANNEL_CPU_AFFINITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - netdma.h
api_name:
 - NET_DMA_CHANNEL_CPU_AFFINITY
---

# _NET_DMA_CHANNEL_CPU_AFFINITY structure


## -description

<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_CHANNEL_CPU_AFFINITY structure specifies the CPU affinity of a DMA channel.

## -struct-fields

### -field DmaChannel

The DMA channel number. The values for this member range from zero through the maximum number of
     DMA channels that the DMA engine supports minus one. The DMA provider driver specifies the maximum
     number of DMA channels in the 
     <b>MaxDmaChannelCount</b> member of the 
     <a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
     NET_DMA_PROVIDER_CHARACTERISTICS</a> structure.

### -field CpuNumber

The target CPU that the DMA provider driver should associate with the MSI-X interrupts that are
     generated for the DMA channel that is specified in the 
     <b>DmaChannel</b> member.

## -remarks

The NetDMA interface passes an array of NET_DMA_CHANNEL_CPU_AFFINITY structures to a DMA provider
    driver's 
    <a href="/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channels_cpu_affinity_handler">
    ProviderSetDmaChannelCpuAffinity</a> function to specify the CPU affinity of the DMA channels.

The NetDMA interface calls 
    <i>ProviderSetDmaChannelCpuAffinity</i> while in the context of the 
    <a href="/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
    NetDmaRegisterProvider</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>



<a href="/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channels_cpu_affinity_handler">
   ProviderSetDmaChannelCpuAffinity</a>
