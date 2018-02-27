---
UID: NA:netdma
ms.assetid: e5a964e4-9c67-3eff-81bc-8f64c553c920
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netdma.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netdma.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetDmaDeregisterProvider function](nf-netdma-netdmaderegisterprovider.md) | The NetDmaDeregisterProvider function deregisters a DMA provider. |
| [NetDmaGetVersion function](nf-netdma-netdmagetversion.md) | Note  The NetDMA interface is not supported in Windows 8 and later. The NetDmaGetVersion function returns the version of the NetDMA interface that the local computer supports. |
| [NetDmaInterruptDpc function](nf-netdma-netdmainterruptdpc.md) | The NetDmaInterruptDpc function notifies the NetDMA interface that a DMA transfer deferred procedure call (DPC) has completed on a DMA channel. |
| [NetDmaIsr function](nf-netdma-netdmaisr.md) | The NetDmaIsr function notifies the NetDMA interface that a DMA transfer interrupt has occurred on a DMA channel. |
| [NetDmaPnPEventNotify function](nf-netdma-netdmapnpeventnotify.md) | The NetDmaPnPEventNotify function indicates a power state change for a NetDMA provider device. |
| [NetDmaProviderStart function](nf-netdma-netdmaproviderstart.md) | The NetDmaProviderStart function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are initialized and ready for DMA transfers. |
| [NetDmaProviderStop function](nf-netdma-netdmaproviderstop.md) | The NetDmaProviderStop function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are no longer available for DMA transfers. |
| [NetDmaRegisterProvider function](nf-netdma-netdmaregisterprovider.md) | The NetDmaRegisterProvider function registers a DMA provider. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [DMA_ABORT_HANDLER callback](nc-netdma-dma_abort_handler.md) | The ProviderAbortDma function cancels any DMA transfers that are associated with a DMA channel. |
| [DMA_APPEND_HANDLER callback](nc-netdma-dma_append_handler.md) | The ProviderAppendDma function appends a linked list of DMA descriptors to the last descriptor on a DMA channel. |
| [DMA_CHANNELS_CPU_AFFINITY_HANDLER callback](nc-netdma-dma_channels_cpu_affinity_handler.md) | The ProviderSetDmaChannelCpuAffinity function sets the CPU affinities for the DMA channels that are associated with a DMA provider. |
| [DMA_CHANNEL_ALLOCATE_HANDLER callback](nc-netdma-dma_channel_allocate_handler.md) | The ProviderAllocateDmaChannel function allocates a DMA channel. |
| [DMA_CHANNEL_FREE_HANDLER callback](nc-netdma-dma_channel_free_handler.md) | The ProviderFreeDmaChannel function frees a DMA channel that the ProviderAllocateDmaChannel function previously allocated. |
| [DMA_RESET_HANDLER callback](nc-netdma-dma_reset_handler.md) | The ProviderResetChannel function resets a DMA channel to the initial state that existed after the DMA channel was allocated. |
| [DMA_RESUME_HANDLER callback](nc-netdma-dma_resume_handler.md) | The ProviderResumeDma function resumes the DMA transfers that are currently suspended on a DMA channel. |
| [DMA_START_HANDLER callback](nc-netdma-dma_start_handler.md) | The ProviderStartDma function starts a DMA transfer on the specified DMA channel. |
| [DMA_SUSPEND_HANDLER callback](nc-netdma-dma_suspend_handler.md) | The ProviderSuspendDma function suspends the DMA transfers that are currently in progress on a DMA channel. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_DMA_CHANNEL_CPU_AFFINITY structure](ns-netdma-_net_dma_channel_cpu_affinity.md) | The NET_DMA_CHANNEL_CPU_AFFINITY structure specifies the CPU affinity of a DMA channel. |
| [_NET_DMA_CHANNEL_PARAMETERS structure](ns-netdma-_net_dma_channel_parameters.md) | The NET_DMA_CHANNEL_PARAMETERS structure specifies the configuration parameters that a DMA provider driver should use to configure a DMA channel. |
| [_NET_DMA_DESCRIPTOR structure](ns-netdma-_net_dma_descriptor.md) | The NET_DMA_DESCRIPTOR structure specifies the DMA transfer information for each entry in a linked list of DMA descriptors. |
| [_NET_DMA_PNP_NOTIFICATION structure](ns-netdma-_net_dma_pnp_notification.md) | The NET_DMA_PNP_NOTIFICATION structure specifies a power management notification in the NetDMA interface. |
| [_NET_DMA_PROVIDER_ATTRIBUTES structure](ns-netdma-_net_dma_provider_attributes.md) | The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration attributes for a NetDMA provider. |
| [_NET_DMA_PROVIDER_CHARACTERISTICS structure](ns-netdma-_net_dma_provider_characteristics.md) | The NET_DMA_PROVIDER_CHARACTERISTICS structure specifies the characteristics for a NetDMA provider, including the entry points for the ProviderXxx functions. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NET_DMA_PNP_NOTIFICATION_CODE enumeration](ne-netdma-_net_dma_pnp_notification_code.md) | The NET_DMA_PNP_NOTIFICATION_CODE enumeration identifies the type of a NetDMA Plug and Play (PnP) event. |
