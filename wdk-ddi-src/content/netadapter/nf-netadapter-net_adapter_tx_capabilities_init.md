---
UID: NF:netadapter.NET_ADAPTER_TX_CAPABILITIES_INIT
title: NET_ADAPTER_TX_CAPABILITIES_INIT function (netadapter.h)
description: The NET_ADAPTER_TX_CAPABILITIES_INIT function initializes a NET_ADAPTER_TX_CAPABILITIES structure for a net adapter that has not specified the use of DMA in its transmit data path.
tech.root: netvista
ms.assetid: 7dbe4ccf-590f-4ab0-8ec7-dff6bd0395f3
ms.date: 09/27/2019
keywords: ["NET_ADAPTER_TX_CAPABILITIES_INIT function"]
ms.keywords: NET_ADAPTER_TX_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header: netadaptercx.h netadaptercx.h
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
 - NET_ADAPTER_TX_CAPABILITIES_INIT
 - netadapter/NET_ADAPTER_TX_CAPABILITIES_INIT
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NET_ADAPTER_TX_CAPABILITIES_INIT
---

# NET_ADAPTER_TX_CAPABILITIES_INIT function


## -description

The **NET_ADAPTER_TX_CAPABILITIES_INIT** function initializes a [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure for a net adapter that has not specified the use of DMA in its transmit data path.

## -parameters

### -param TxCapabilities

A pointer to a driver-allocated [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure.

### -param MaximumNumberOfQueues

The maximum number of transmit queues that the adapter supports.

## -returns

This function does not return a value.

## -remarks

This function is one of two possible functions to call in order to initialize a [NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md) structure. Which one the client driver should call depends on whether it would like to use DMA. **NET_ADAPTER_TX_CAPABILITIES_INIT** is used if the driver does not specify DMA memory mapping for its transmit buffers, and [NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA](nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md) is used if it does.

## -see-also

[NET_ADAPTER_TX_CAPABILITIES](ns-netadapter-_net_adapter_tx_capabilities.md)

[NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA](nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md)

