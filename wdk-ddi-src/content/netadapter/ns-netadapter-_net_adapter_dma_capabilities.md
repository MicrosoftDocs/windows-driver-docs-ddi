---
UID: NS:netadapter._NET_ADAPTER_DMA_CAPABILITIES
title: _NET_ADAPTER_DMA_CAPABILITIES
author: windows-driver-content
description: The NET_ADAPTER_DMA_CAPABILITIES structure describes the DMA capabilities of an adapter.
ms.assetid: b0b5cd8b-807c-42d2-9f6b-4843f82c6309
ms.author: windowsdriverdev
ms.date: 02/14/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_DMA_CAPABILITIES, *PNET_ADAPTER_DMA_CAPABILITIES, NET_ADAPTER_DMA_CAPABILITIES, 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_DMA_CAPABILITIES, *PNET_ADAPTER_DMA_CAPABILITIES
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	_NET_ADAPTER_DMA_CAPABILITIES
product:
-	Windows
targetos: Windows
---

# _NET_ADAPTER_DMA_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_ADAPTER_DMA_CAPABILITIES** structure describes the DMA capabilities of a net adapter.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field DmaEnabler
The DMA enabler object used by the client driver to map and allocate memory.
 
### -field MaximumPhysicalAddress
The maximum physical address to use when allocating memory buffers. Set this member to **0** to indicate that there is no maximum address.

### -field MaximumNumberOfPhysicalFragments
The maximum number of physical fragments per packet the adapter can handle. Set this member to `((LONGLONG) - 1)` if there is no limit.

### -field CacheEnabled
A [WDF_TRI_STATE](../wdftypes/ne-wdftypes-_wdf_tri_state.md) value that defines if the memory allocated should have cache enabled or not. If this member is set to **WdfDefault**, cache will be enabled only if the device is cache coherent.
 
### -field PreferredNode
The preferred NUMA node to use when allocating memory. If this member is set to MM_ANY_NODE_OK, NetAdapterCx will automatically determine the best node to use.

## -remarks
Call [NET_ADAPTER_DMA_CAPABILITIES_INIT](nf-netadapter-net_adapter_dma_capabilities_init.md) to initialize this structure.

This structure can be used either in Rx queues, as a member of the [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure, or in Tx queues, as a member of the [NET_ADAPTER_TX_CAPABILITIES](nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md) structure.



## -see-also

[NET_ADAPTER_DMA_CAPABILITIES_INIT](nf-netadapter-net_adapter_dma_capabilities_init.md)

[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)

[NET_ADAPTER_TX_CAPABILITIES](nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md)