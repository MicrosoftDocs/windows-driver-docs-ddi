---
UID: NF:netadapter.NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED
title: NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED function (netadapter.h)
description: The NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify operating system-managed receive buffer allocation and attachment, but not the use of DMA memory mapping.
tech.root: netvista
ms.assetid: 552987ea-44d8-4330-a9e8-3f1c3d0e5590
ms.date: 02/15/2018
ms.topic: function
f1_keywords:
 - "netadapter/NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED"
ms.keywords: NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
- NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED
product:
- Windows
targetos: Windows

---

# NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED function


## -description



The **NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED** method initializes a [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure for a net adapter that would like to specify operating system-managed receive buffer allocation and attachment, but not the use of DMA memory mapping.

## -parameters

### -param RxCapabilities
A pointer to a driver-allocated [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure.

### -param MaximumFragmentBufferSize
The maximum fragment buffer size, in bytes, that the adapter can receive.

### -param MaximumNumberOfQueues
The maximum number of receive queues that the adapter supports.

## -returns
This method does not return a value.

## -remarks
This method is one of three possible methods to call in order to initialize a [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure. Which one the client driver should call depends on how it would like to allocate receive buffers and if it would like to use DMA.

The client driver must call **NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED** to initialize its **NET_ADAPTER_RX_CAPABILITIES** structure if it would like the operating system to perform receive buffer allocation and attachment, but does not require DMA memory mapping. By calling this method, the Rx capabilities structure's **AllocationMode** member is set to **NetRxFragmentBufferAllocationModeSystem** and the **AttachmentMode** member is set to **NetRxFragmentBufferAttachmentModeSystem**. Because the driver does not specify DMA capabilities in this case, this method also sets the **MappingRequirement** member to **NetMemoryMappingRequirementNone**. 



## -see-also
[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA](nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md)
