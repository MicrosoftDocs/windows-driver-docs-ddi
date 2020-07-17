---
UID: NF:netadapter.NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA
title: NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA function (netadapter.h)
description: The NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify operating system-managed receive buffer allocation and attachment, as well as DMA for memory mapping.
tech.root: netvista
ms.assetid: 784695e1-dd5f-49ab-b72d-31857b1f13aa
ms.date: 02/14/2018
keywords: ["NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA function"]
f1_keywords:
 - "netadapter/NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA"
 - "NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA"
ms.keywords: NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA
product:
- Windows
targetos: Windows
---

# NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA function


## -description



The **NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA** method initializes a [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure for a net adapter that would like to specify operating system-managed receive buffer allocation and attachment, as well as DMA for memory mapping.

## -parameters

### -param RxCapabilities
A pointer to a driver-allocated [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure.

### -param DmaCapabilities
A pointer to a driver-allocated and initialized [NET_ADAPTER_DMA_CAPABILITIES](ns-netadapter-_net_adapter_dma_capabilities.md) structure.

### -param MaximumFragmentBufferSize
The maximum fragment buffer size, in bytes, that the adapter can receive.

### -param MaximumNumberOfQueues
The maximum number of receive queues that the adapter supports.

## -remarks
This method is one of three possible methods to call in order to initialize a [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Which one the client driver should call depends on how it would like to allocate receive buffers and if it would like to use DMA.

The client driver must call **NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA** to initialize its **NET_ADAPTER_RX_CAPABILITIES** structure if it would like the operating system to perform receive buffer allocation and attachment, and if it would also like to use DMA in its receive data path. By calling this method, the Rx capabilities structure's **AllocationMode** member is set to **NetRxFragmentBufferAllocationModeSystem** and the **AttachmentMode** member is set to **NetRxFragmentBufferAttachmentModeSystem**. 

Before calling **NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA**, the driver must have allocated a [NET_ADAPTER_DMA_CAPABILITIES](ns-netadapter-_net_adapter_dma_capabilities.md) structure and initialized it with [NET_ADAPTER_DMA_CAPABILITIES_INIT](nf-netadapter-net_adapter_dma_capabilities_init.md). This DMA capabilities structure is then assigned to the **DmaCapabilities** member of the **NET_ADAPTER_RX_CAPABILITIES** structure.



## -see-also
[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_system_managed.md)
