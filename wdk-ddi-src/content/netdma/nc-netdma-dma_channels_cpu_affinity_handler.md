---
UID: NC:netdma.DMA_CHANNELS_CPU_AFFINITY_HANDLER
title: DMA_CHANNELS_CPU_AFFINITY_HANDLER (netdma.h)
description: The ProviderSetDmaChannelCpuAffinity function sets the CPU affinities for the DMA channels that are associated with a DMA provider.
old-location: netvista\providersetdmachannelcpuaffinity.htm
tech.root: netvista
ms.assetid: a53d8798-63fa-4b16-bda2-880ca3521d03
ms.date: 05/02/2018
keywords: ["DMA_CHANNELS_CPU_AFFINITY_HANDLER callback function"]
ms.keywords: DMA_CHANNELS_CPU_AFFINITY_HANDLER, DMA_CHANNELS_CPU_AFFINITY_HANDLER callback, ProviderSetDmaChannelCpuAffinity, ProviderSetDmaChannelCpuAffinity callback function [Network Drivers Starting with Windows Vista], netdma/ProviderSetDmaChannelCpuAffinity, netdma_ref_bda3a4d0-7039-4f29-b75c-1e7e4a8f2131.xml, netvista.providersetdmachannelcpuaffinity
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DMA_CHANNELS_CPU_AFFINITY_HANDLER
 - netdma/DMA_CHANNELS_CPU_AFFINITY_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - netdma.h
api_name:
 - ProviderSetDmaChannelCpuAffinity
---

# DMA_CHANNELS_CPU_AFFINITY_HANDLER callback function


## -description

<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderSetDmaChannelCpuAffinity</i> function sets the CPU affinities for the DMA channels that are
  associated with a DMA provider.

## -parameters

### -param ProviderContext 

[in]
A pointer that identifies a DMA provider's context area. The DMA provider driver passed this
     pointer to NetDMA in a call to the 
     <a href="/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
     NetDmaRegisterProvider</a> function.

### -param CpuAffinityArray 

[in]
A pointer to an array of 
     <a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_cpu_affinity">
     NET_DMA_CHANNEL_CPU_AFFINITY</a> structures that specify the CPU affinities for the DMA channels that
     are associated with the DMA provider.

### -param CpuAffinityArraySize 

[in]
The length, in bytes, of the buffer at 
     <i>CpuAffinityArray</i> .

## -returns

<i>ProviderSetDmaChannelCpuAffinity</i> returns one of the following status values:

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
<dt><b>STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

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

The NetDMA interface calls a DMA provider driver's 
    <i>ProviderSetDmaChannelCpuAffinity</i> function to specify the CPU affinities of a DMA provider's DMA
    channels. NetDMA calls 
    <i>ProviderSetDmaChannelCpuAffinity</i> while in the context of the 
    <a href="/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
    NetDmaRegisterProvider</a> function.

Because the actual number of DMA channels is not known before a DMA provider is started, the NetDMA
    interface specifies the CPU affinities for the maximum number of channels. The DMA provider supplies the
    maximum number of channels in the 
    <b>MaxDmaChannelCount</b> member of the 
    <a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
    NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that it passes to the 
    <b>NetDmaRegisterProvider</b> function.

On computers that do not support MSI-X platforms, CPU affinities can be specified for the interrupt
    DPCs but not for the interrupts. In this case, the NetDMA interface specifies a list of possible CPUs for
    the interrupt DPC in the 
    <b>ProcessorAffinityMask</b> member of the 
    <a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_parameters">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

On computers that do support MSI-X, the DMA provider driver can specify interrupt affinities while
    handling the 
    <a href="/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
    IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> IRP.

NetDMA calls 
    <i>ProviderSetDmaChannelCpuAffinity</i> at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_cpu_affinity">NET_DMA_CHANNEL_CPU_AFFINITY</a>



<a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_channel_parameters">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>