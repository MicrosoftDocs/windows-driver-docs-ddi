---
UID: NF:netadapter.NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA
title: NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA function (netadapter.h)
description: The NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA function initializes a NET_ADAPTER_TX_CAPABILITIES structure for a net adapter that has specified the use of DMA in its transmit data path.
tech.root: netvista
ms.date: 09/27/2019
keywords: ["NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA function"]
ms.keywords: NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.25
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA
 - netadapter/NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA
---

# NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA function


## -description

The **NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA** function initializes a [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure for a net adapter that has specified the use of DMA in its transmit data path.

## -parameters

### -param TxCapabilities

A pointer to a driver-allocated [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure.

### -param DmaCapabilities

A pointer to a driver-allocated and initialized [NET_ADAPTER_DMA_CAPABILITIES](ns-netadapter-_net_adapter_dma_capabilities.md) structure.

### -param MaximumNumberOfQueues

The maximum number of transmit queues that the adapter supports.

## -returns

This function does not return a value.

## -remarks

This function is one of two possible functions to call in order to initialize a [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure. Which one the client driver should call depends on whether it would like to use DMA. [NET_ADAPTER_TX_CAPABILITIES_INIT](nf-netadapter-net_adapter_tx_capabilities_init.md) is used if the driver does not specify DMA memory mapping for its transmit buffers, and **NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA** is used if it does.

Before calling **NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA**, the driver must have allocated a [NET_ADAPTER_DMA_CAPABILITIES](ns-netadapter-_net_adapter_dma_capabilities.md) structure and initialized it with [NET_ADAPTER_DMA_CAPABILITIES_INIT](nf-netadapter-net_adapter_dma_capabilities_init.md). This DMA capabilities structure is then assigned to the **DmaCapabilities** member of the **NET_ADAPTER_TX_CAPABILITIES** structure.

## -see-also

[NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md)

[NET_ADAPTER_TX_CAPABILITIES_INIT](nf-netadapter-net_adapter_tx_capabilities_init.md)

