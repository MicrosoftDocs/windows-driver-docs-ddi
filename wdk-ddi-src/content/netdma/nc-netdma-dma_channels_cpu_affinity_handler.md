---
UID: NC:netdma.DMA_CHANNELS_CPU_AFFINITY_HANDLER
title: DMA_CHANNELS_CPU_AFFINITY_HANDLER
author: windows-driver-content
description: The ProviderSetDmaChannelCpuAffinity function sets the CPU affinities for the DMA channels that are associated with a DMA provider.
old-location: netvista\providersetdmachannelcpuaffinity.htm
old-project: netvista
ms.assetid: a53d8798-63fa-4b16-bda2-880ca3521d03
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _MIRACAST_DRIVER_INTERFACE, MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
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
req.alt-api: ProviderSetDmaChannelCpuAffinity
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
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_CHANNELS_CPU_AFFINITY_HANDLER callback



## -description

## -prototype

````
DMA_CHANNELS_CPU_AFFINITY_HANDLER ProviderSetDmaChannelCpuAffinity;

NTSTATUS ProviderSetDmaChannelCpuAffinity(
  _In_ PVOID                         ProviderContext,
  _In_ PNET_DMA_CHANNEL_CPU_AFFINITY CpuAffinityArray,
  _In_ ULONG                         CpuAffinityArraySize
)
{ ... }
````


## -parameters

### -param ProviderContext [in]

A pointer that identifies a DMA provider's context area. The DMA provider driver passed this
     pointer to NetDMA in a call to the 
     <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
     NetDmaRegisterProvider</a> function.


### -param CpuAffinityArray [in]

A pointer to an array of 
     <a href="..\netdma\ns-netdma-_net_dma_channel_cpu_affinity.md">
     NET_DMA_CHANNEL_CPU_AFFINITY</a> structures that specify the CPU affinities for the DMA channels that
     are associated with the DMA provider.


### -param CpuAffinityArraySize [in]

The length, in bytes, of the buffer at 
     <i>CpuAffinityArray</i> .


## -returns
<i>ProviderSetDmaChannelCpuAffinity</i> returns one of the following status values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>STATUS_RESOURCES</b></dt>
</dl>The operation failed because of insufficient resources.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The operation failed for unspecified reasons.

 


## -remarks
The NetDMA interface calls a DMA provider driver's 
    <i>ProviderSetDmaChannelCpuAffinity</i> function to specify the CPU affinities of a DMA provider's DMA
    channels. NetDMA calls 
    <i>ProviderSetDmaChannelCpuAffinity</i> while in the context of the 
    <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
    NetDmaRegisterProvider</a> function.

Because the actual number of DMA channels is not known before a DMA provider is started, the NetDMA
    interface specifies the CPU affinities for the maximum number of channels. The DMA provider supplies the
    maximum number of channels in the 
    <b>MaxDmaChannelCount</b> member of the 
    <a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
    NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that it passes to the 
    <b>NetDmaRegisterProvider</b> function.

On computers that do not support MSI-X platforms, CPU affinities can be specified for the interrupt
    DPCs but not for the interrupts. In this case, the NetDMA interface specifies a list of possible CPUs for
    the interrupt DPC in the 
    <b>ProcessorAffinityMask</b> member of the 
    <a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">
    NET_DMA_CHANNEL_PARAMETERS</a> structure.

On computers that do support MSI-X, the DMA provider driver can specify interrupt affinities while
    handling the 
    <a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
    IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> IRP.

NetDMA calls 
    <i>ProviderSetDmaChannelCpuAffinity</i> at IRQL = PASSIVE_LEVEL.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>
</dt>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_channel_cpu_affinity.md">NET_DMA_CHANNEL_CPU_AFFINITY</a>
</dt>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">NET_DMA_CHANNEL_PARAMETERS</a>
</dt>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_provider_characteristics.md">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_CHANNELS_CPU_AFFINITY_HANDLER callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

