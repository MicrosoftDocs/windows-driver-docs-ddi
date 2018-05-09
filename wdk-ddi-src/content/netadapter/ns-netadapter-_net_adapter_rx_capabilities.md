---
UID: NS:netadapter._NET_ADAPTER_RX_CAPABILITIES
title: _NET_ADAPTER_RX_CAPABILITIES
author: windows-driver-content
description: The NET_ADAPTER_RX_CAPABILITIES structure describes the receive capabilities of a net adapter.
ms.assetid: 32a95b23-291f-4cee-a836-33cd7dba5149
ms.author: windowsdriverdev
ms.date: 02/14/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_RX_CAPABILITIES, NET_ADAPTER_RX_CAPABILITIES, *PNET_ADAPTER_RX_CAPABILITIES, 
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
req.typenames: NET_ADAPTER_RX_CAPABILITIES, *PNET_ADAPTER_RX_CAPABILITIES
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	_NET_ADAPTER_RX_CAPABILITIES
product: Windows
targetos: Windows
---

# _NET_ADAPTER_RX_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The NET_ADAPTER_RX_CAPABILITIES structure describes the receive capabilities of a net adapter.

## -struct-fields

### -field Size
The size of this structure, in bytes.

### -field AllocationMode
A [NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md) value that specifies how the operating system should allocate receive buffers.

### -field AttachmentMode
A [NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE](ne-netadapter-_net_rx_fragment_buffer_attachment_mode.md) value that specifies how the operating system should pre-attach receive buffers.

### -field FragmentRingNumberOfElementsHint
A hint indicating how many elements the adapter wants for each receive queue's ring buffer of [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md)s. This member must be a power of 2.

### -field MaximumFragmentBufferSize
The maximum fragment buffer size, in bytes, that the adapter can receive.
 
### -field MaximumNumberOfQueues
The maximum number of receive queues that the adapter supports.

### -field DUMMYUNIONNAME
A union that contains the following members:

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME
A struct that contains the following member:

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EvtAdapterReturnRxBuffer
A pointer to the driver's *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function. This member is required if the **AllocationMode** member is set to **NetRxFragmentBufferAllocationModeDriver** for the operating system to invoke once the system is finished with the receive buffer.

For more information about *EvtNetAdapterReturnRxBuffer*, see the Remarks section of [**NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED**](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md).

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2
A struct that contains the following members:
 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2.MappingRequirement
A [NET_MEMORY_MAPPING_REQUIREMENT](ne-netadapter-_net_memory_mapping_requirement.md) value that specifies how the operating system should map receive data buffers.
 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2.FragmentBufferAlignment
The minimum alignment for packet fragments. This member must be a power of 2.
 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2.DmaCapabilities
A pointer to a driver-allocated and initialized [NET_DMA_CAPABILITIES](ns-netadapter-_net_adapter_dma_capabilities.md) structure that describes the adapter's DMA capabilities on the receive path. This member is ignored by NetAdapterCx if **MappingRequirement** is not set to **NetMemoryMappingRequirementDmaMapped**.

## -remarks
Call one of the NET_ADAPTER_RX_CAPABILITIES_INIT_*XXX* methods to initialize this structure. For more info about each initialization method, see the links in the See Also section. An initialized **NET_ADAPTER_RX_CAPABILITIES** structure is passed as a parameter to [NetAdapterSetDatapathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md).

After initializing this structure, client drivers must be careful about changing the **AllocationMode** and **AttachmentMode** members. If **AllocationMode** is set to **NetRxFragmentBufferAllocationModeDriver**, then **AttachmentMode** cannot be set to **NetRxFragmentBufferAttachmentModeSystem**. If **AllocationMode** is set to **NetRxFragmentBufferAllocationModeSystem**, it is possible for the driver to specify manual attachment after initialization by setting **AttachmentMode** to **NetRxFragmentBufferAttachmentModeDriver**. Typically, however, the driver will either perform both allocation and attachmment itself or will specify that the operating system perform both.

If the client does specify driver-allocated and attached receive buffers, it must supply both a custom return context structure in the **RxBufferReturnContext** member of each [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) during buffer allocation, as well as an *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function in this **NET_ADAPTER_RX_CAPABILITIES** structure for the operating system to invoke once it has finished with the buffer.

For more information about *EvtNetAdapterReturnRxBuffer*, see the Remarks section of [**NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED**](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md).

The minimum NetAdapterCx version for **NET_ADAPTER_RX_CAPABILITIES** is 1.2.

## -see-also
[NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_system_managed.md)

[NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA](nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md)

[NetAdapterSetDatapathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md)