---
UID: NS:netadapter._NET_ADAPTER_RX_CAPABILITIES
title: _NET_ADAPTER_RX_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_RX_CAPABILITIES structure describes the receive capabilities of a net adapter.
tech.root: netvista
ms.assetid: 32a95b23-291f-4cee-a836-33cd7dba5149
ms.date: 02/14/2018
keywords: ["_NET_ADAPTER_RX_CAPABILITIES structure"]
f1_keywords:
 - "netadapter/NET_ADAPTER_POWER_CAPABILITIES"
 - "NET_ADAPTER_POWER_CAPABILITIES"
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
- apiref
apitype: 
- HeaderDef
apilocation: 
- netadapter.h
apiname: 
- _NET_ADAPTER_RX_CAPABILITIES
product:
- Windows
targetos: Windows
---

# _NET_ADAPTER_RX_CAPABILITIES structure

## -description



The **NET_ADAPTER_RX_CAPABILITIES** structure describes the receive capabilities of a net adapter.

## -struct-fields

### -field Size
The size of this structure, in bytes.

### -field AllocationMode
A [**NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE**](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md) value that specifies how the operating system should allocate receive buffers.

### -field AttachmentMode
A [**NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE**](ne-netadapter-_net_rx_fragment_buffer_attachment_mode.md) value that specifies how the operating system should pre-attach receive buffers.

### -field FragmentRingNumberOfElementsHint
A hint indicating how many elements the adapter wants for each receive queue's ring buffer of [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)s. This member must be a power of 2.

### -field MaximumFragmentBufferSize
The maximum fragment buffer size, in bytes, that the adapter can receive. This value should include the maximum transmission unit (MTU) size that your hardware supports for an IP packet, plus additional space your driver might need for packet metadata. For more information, see the receive example in the Remarks section of [*EVT_PACKET_QUEUE_ADVANCE*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_advance.md).
 
### -field MaximumNumberOfQueues
The maximum number of receive queues that the adapter supports.

### -field DUMMYUNIONNAME
A union that contains the following members:

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME
A struct that contains the following member:

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.EvtAdapterReturnRxBuffer
A pointer to the driver's [*EVT_NET_ADAPTER_RETURN_RX_BUFFER*](nc-netadapter-evt_net_adapter_return_rx_buffer.md) callback function. This member is required if the **AllocationMode** member is set to **NetRxFragmentBufferAllocationModeDriver** for the operating system to invoke once the system is finished with the receive buffer.

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2
A struct that contains the following members:
 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2.MappingRequirement
A [**NET_MEMORY_MAPPING_REQUIREMENT**](ne-netadapter-_net_memory_mapping_requirement.md) value that specifies how the operating system should map receive data buffers.
 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2.FragmentBufferAlignment
The minimum alignment for packet fragments. This member must be a power of 2.
 
### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME2.DmaCapabilities
A pointer to a driver-allocated and initialized [**NET_DMA_CAPABILITIES**](ns-netadapter-_net_adapter_dma_capabilities.md) structure that describes the adapter's DMA capabilities on the receive path. This member is ignored by NetAdapterCx if **MappingRequirement** is not set to **NetMemoryMappingRequirementDmaMapped**.

## -remarks
Call one of the NET_ADAPTER_RX_CAPABILITIES_INIT_*XXX* methods to initialize this structure. For more info about each initialization method, see the links in the See Also section. An initialized **NET_ADAPTER_RX_CAPABILITIES** structure is passed as a parameter to [**NetAdapterSetDatapathCapabilities**](nf-netadapter-netadaptersetdatapathcapabilities.md).

Typically, a client driver either performs both allocation and attachmment itself or specifies that the operating system perform both. In most cases, we recommend that the operating system allocates and attaches receive buffers.

If the client does specify driver-allocated and attached receive buffers, it must supply both a custom return context structure in the **RxBufferReturnContext** member of each [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) during buffer allocation, as well as an *EVT_NET_ADAPTER_RETURN_RX_BUFFER* callback function in this **NET_ADAPTER_RX_CAPABILITIES** structure for the operating system to invoke once it has finished with the buffer.

## -see-also

[**NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED**](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md)

[**NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED**](nf-netadapter-net_adapter_rx_capabilities_init_system_managed.md)

[**NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA**](nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md)

[**NetAdapterSetDatapathCapabilities**](nf-netadapter-netadaptersetdatapathcapabilities.md)
