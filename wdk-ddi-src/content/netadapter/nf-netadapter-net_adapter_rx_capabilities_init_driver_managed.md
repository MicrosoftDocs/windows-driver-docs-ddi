---
UID: NF:netadapter.NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED
title: NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED function (netadapter.h)
description: The NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify driver-managed receive buffer allocation and attachment.
tech.root: netvista
ms.assetid: d3b29896-25ef-4d96-99db-799408fb207f
ms.date: 02/14/2018
keywords: ["NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED function"]
f1_keywords:
 - "netadapter/NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED"
 - "NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED"
ms.keywords: NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED
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
- NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED
targetos: Windows
---

# NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED function


## -description



The **NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED** method initializes a [**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md) structure for a net adapter that would like to specify driver-managed receive buffer allocation and attachment.

## -parameters

### -param RxCapabilities
A pointer to a driver-allocated [**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md) structure.

### -param EvtAdapterReturnRxBuffer
A pointer to the client driver's *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function. For more information, see the Remarks section.

### -param MaximumFragmentBufferSize
The maximum fragment buffer size, in bytes, that the adapter can receive.

### -param MaximumNumberOfQueues
The maximum number of receive queues that the adapter supports.

## -remarks
This method is one of three possible methods to call in order to initialize a [**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Which one the client driver should call depends on how it would like to allocate receive buffers and if it would like to use DMA.

The client driver must call **NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED** to initialize its **NET_ADAPTER_RX_CAPABILITIES** structure if it would like to perform manual receive buffer allocation and attachment. By calling this method, the Rx capabilities structure's **AllocationMode** member is set to **NetRxFragmentBufferAllocationModeDriver** and the **AttachmentMode** member is set to **NetRxFragmentBufferAttachmentModeDriver**. In this case, it must also provide a pointer to its *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function in the structure for the operating system to invoke once the system has finished with the receive buffer.

## -see-also

[**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md)

[**NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED**](nf-netadapter-net_adapter_rx_capabilities_init_system_managed.md)

[**NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA**](nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md)
