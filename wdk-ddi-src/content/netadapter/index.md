---
UID: NA:netadapter
ms.assetid: a8daa0fe-db44-3a6f-a53f-7c78c290341e
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netadapter.h header



This header is used by NetAdapterCx client drivers. For more information, see
- [Network Adapter WDF Class Extension (Cx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/)

Netadapter.h contains these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NET_ADAPTER_CONFIG_INIT function](nf-netadapter-net_adapter_config_init.md) | Initializes the NET_ADAPTER_CONFIG structure. |
| [NET_ADAPTER_DMA_CAPABILITIES_INIT function](nf-netadapter-net_adapter_dma_capabilities_init.md) | The NET_ADAPTER_DMA_CAPABILITIES_INIT method initializes a NET_ADAPTER_DMA_CAPABILITIES structure. |
| [NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function](nf-netadapter-net_adapter_link_layer_address_init.md) | The NET_ADAPTER_LINK_LAYER_ADDRESS_INIT method initializes a link layer address. |
| [NET_ADAPTER_LINK_LAYER_CAPABILITIES_INIT function](nf-netadapter-net_adapter_link_layer_capabilities_init.md) | Initializes the NET_ADAPTER_LINK_LAYER_CAPABILITIES structure. |
| [NET_ADAPTER_LINK_STATE_INIT function](nf-netadapter-net_adapter_link_state_init.md) | Initializes a NET_ADAPTER_LINK_STATE structure. |
| [NET_ADAPTER_LINK_STATE_INIT_DISCONNECTED function](nf-netadapter-net_adapter_link_state_init_disconnected.md) | Initializes a NET_ADAPTER_LINK_STATE structure for an adapter that is disconnected from the network. |
| [NET_ADAPTER_POWER_CAPABILITIES_INIT function](nf-netadapter-net_adapter_power_capabilities_init.md) | Initializes a NET_ADAPTER_POWER_CAPABILITIES structure. |
| [NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED function](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md) | The NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify driver-managed receive buffer allocation and attachment. |
| [NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED function](nf-netadapter-net_adapter_rx_capabilities_init_system_managed.md) | The NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify operating system-managed receive buffer allocation and attachment, but not the use of DMA memory mapping. |
| [NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA function](nf-netadapter-net_adapter_rx_capabilities_init_system_managed_dma.md) | The NET_ADAPTER_RX_CAPABILITIES_INIT_SYSTEM_MANAGED_DMA method initializes a NET_ADAPTER_RX_CAPABILITIES structure for a net adapter that would like to specify operating system-managed receive buffer allocation and attachment, as well as DMA for memory mapping. |
| [NET_ADAPTER_TX_CAPABILITIES_INIT function](nf-netadapter-net_adapter_tx_capabilities_init.md) | The NET_ADAPTER_TX_CAPABILITIES_INIT method initializes a NET_ADAPTER_TX_CAPABILITIES structure for a net adapter that has not specified the use of DMA in its transmit data path. |
| [NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA function](nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md) | The NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA method initializes a NET_ADAPTER_TX_CAPABILITIES structure for a net adapter that has specified the use of DMA in its transmit data path. |
| [NetAdapterCreate function](nf-netadapter-netadaptercreate.md) | Creates a net adapter object. |
| [NetAdapterDeviceInitConfig function](nf-netadapter-netadapterdeviceinitconfig.md) | Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device. |
| [NetAdapterDriverWdmGetHandle function](nf-netadapter-netadapterdriverwdmgethandle.md) | A WDF client driver calls NetAdapterDriverWdmGetHandle to get a handle that can be used to call NDIS APIs. |
| [NetAdapterGetNetLuid function](nf-netadapter-netadaptergetnetluid.md) | Retrieves the NET_LUID that is assigned to a network adapter. |
| [NetAdapterGetPowerSettings function](nf-netadapter-netadaptergetpowersettings.md) | Retrieves the NETPOWERSETTINGS object that is associated with a net adapter. |
| [NetAdapterOpenConfiguration function](nf-netadapter-netadapteropenconfiguration.md) | Opens the adapter’s configuration database. |
| [NetAdapterSetCurrentLinkLayerAddress function](nf-netadapter-netadaptersetcurrentlinklayeraddress.md) | The NetAdapterSetCurrentLinkLayerAddress method sets the current link layer address for the network adapter. |
| [NetAdapterSetCurrentLinkState function](nf-netadapter-netadaptersetcurrentlinkstate.md) | Sets the current link state of the of the network adapter. |
| [NetAdapterSetDataPathCapabilities function](nf-netadapter-netadaptersetdatapathcapabilities.md) | Sets the data path capabilities of the network adapter. |
| [NetAdapterSetLinkLayerCapabilities function](nf-netadapter-netadaptersetlinklayercapabilities.md) | Sets the link layer capabilities of the network adapter. |
| [NetAdapterSetLinkLayerMtuSize function](nf-netadapter-netadaptersetlinklayermtusize.md) | Sets the link layer maximum transfer unit size of the adapter. |
| [NetAdapterSetPermanentLinkLayerAddress function](nf-netadapter-netadaptersetpermanentlinklayeraddress.md) | The NetAdapterSetPermanentLinkLayerAddress method sets the permanent link layer address for the network adapter. |
| [NetAdapterSetPowerCapabilities function](nf-netadapter-netadaptersetpowercapabilities.md) | Sets the power capabilities of the network adapter. |
| [NetAdapterStart function](nf-netadapter-netadapterstart.md) | The NetAdapterStart method starts a previously stopped NETADAPTER object. |
| [NetAdapterStop function](nf-netadapter-netadapterstop.md) | The NetAdapterStop method stops a NETADAPTER object. |
| [NetAdapterWdmGetNdisHandle function](nf-netadapter-netadapterwdmgetndishandle.md) | Retrieves the NDIS adapter handle for a specified net adapter. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP callback function](nc-netadapter-evt_net_adapter_create_rssqueue_group.md) | The EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP callback function is reserved for system use. Do not implement this callback in your code. |
| [EVT_NET_ADAPTER_CREATE_RXQUEUE callback function](nc-netadapter-evt_net_adapter_create_rxqueue.md) | The client driver's implementation of the EvtNetAdapterCreateRxQueue event callback function that sets up a receive (Rx) queue. |
| [EVT_NET_ADAPTER_CREATE_TXQUEUE callback function](nc-netadapter-evt_net_adapter_create_txqueue.md) | The client driver's implementation of the *EvtNetAdapterCreateTxQueue* event callback function that sets up a transmit (Tx) queue. |
| [EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD callback function](nc-netadapter-evt_net_adapter_preview_protocol_offload.md) | Implement this optional callback to reject protocol offloads that are not compatible with your hardware. |
| [EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN callback function](nc-netadapter-evt_net_adapter_preview_wake_pattern.md) | Implement this optional callback to reject wake patterns that are not compatible with your hardware. |
| [EVT_NET_ADAPTER_RETURN_RX_BUFFER callback function](nc-netadapter-evt_net_adapter_return_rx_buffer.md) | Implement this optional callback function to perform cleanup on a receive buffer for which you previously specified manual fragment allocation and attachment. |
| [EVT_NET_ADAPTER_SET_CAPABILITIES callback function](nc-netadapter-evt_net_adapter_set_capabilities.md) | The client driver's implementation of the EVT_NET_ADAPTER_SET_CAPABILITIES event callback function that sets the capabilities of the network adapter. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NET_ADAPTER_CONFIG structure](ns-netadapter-_net_adapter_config.md) | Describes the configuration options for a NetAdapterCx client driver. An initialized NET_ADAPTER_CONFIG structure is an input parameter to NetAdapterCreate. |
| [_NET_ADAPTER_DMA_CAPABILITIES structure](ns-netadapter-_net_adapter_dma_capabilities.md) | The NET_ADAPTER_DMA_CAPABILITIES structure describes the DMA capabilities of an adapter. |
| [_NET_ADAPTER_LINK_LAYER_CAPABILITIES structure](ns-netadapter-_net_adapter_link_layer_capabilities.md) | Describes the link layer capabilities of the adapter. |
| [_NET_ADAPTER_LINK_STATE structure](ns-netadapter-_net_adapter_link_state.md) | Describes the link state of the adapter. |
| [_NET_ADAPTER_POWER_CAPABILITIES structure](ns-netadapter-_net_adapter_power_capabilities.md) | Describes the power capabilities of the adapter. |
| [_NET_ADAPTER_RX_CAPABILITIES structure](ns-netadapter-_net_adapter_rx_capabilities.md) | The NET_ADAPTER_RX_CAPABILITIES structure describes the receive capabilities of a net adapter. |
| [_NET_ADAPTER_TX_CAPABILITIES structure](ns-netadapter-_net_adapter_tx_capabilities.md) | The NET_ADAPTER_TX_CAPABILITIES structure describes the transmit capabilities of a net adapter. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NET_ADAPTER_AUTO_NEGOTIATION_FLAGS enumeration](ne-netadapter-_net_adapter_auto_negotiation_flags.md) | Specifies the auto-negotiation settings for the NIC driver. |
| [_NET_ADAPTER_MEDIA_SPECIFIC_WAKEUP_EVENTS_FLAGS enumeration](ne-netadapter-_net_adapter_media_specific_wakeup_events_flags.md) | Specifies the media-specific wake-up events that a network adapter supports. |
| [_NET_ADAPTER_PAUSE_FUNCTIONS enumeration](ne-netadapter-_net_adapter_pause_functions.md) | Specifies a client driver's support for the IEEE 802.3 pause frames. |
| [_NET_ADAPTER_POWER_FLAGS enumeration](ne-netadapter-_net_adapter_power_flags.md) | Specifies a client driver's power capabilities. |
| [_NET_ADAPTER_PROTOCOL_OFFLOADS_FLAGS enumeration](ne-netadapter-_net_adapter_protocol_offloads_flags.md) | Specifies the low power protocol offload capabilities of a network adapter. |
| [_NET_ADAPTER_STATISTICS_FLAGS enumeration](ne-netadapter-_net_adapter_statistics_flags.md) | Specifies statistics that an adapter supports. |
| [_NET_ADAPTER_WAKEUP_EVENTS_FLAGS enumeration](ne-netadapter-_net_adapter_wakeup_events_flags.md) | Specifies the media-independent wake-up events that a network adapter supports. |
| [_NET_ADAPTER_WAKE_PATTERN_FLAGS enumeration](ne-netadapter-_net_adapter_wake_pattern_flags.md) | Specifies wake patterns that an adapter supports. |
| [_NET_MEMORY_MAPPING_REQUIREMENT enumeration](ne-netadapter-_net_memory_mapping_requirement.md) | The NET_MEMORY_MAPPING_REQUIREMENT enumeration identifies the memory mapping requirement that a net adapter can specify for its receive and transmit buffers. |
| [_NET_PACKET_FILTER_TYPES_FLAGS enumeration](ne-netadapter-_net_packet_filter_types_flags.md) | Specifies packet filters that control the types of packets the NIC completes on its receive path. |
| [_NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE enumeration](ne-netadapter-_net_rx_fragment_buffer_allocation_mode.md) | The NET_RX_FRAGMENT_BUFFER_ALLOCATION_MODE enumeration identifies how the operating system should allocate NET_PACKET_FRAGMENT receive buffers for a net adapter client driver's receive queues. |
| [_NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration](ne-netadapter-_net_rx_fragment_buffer_attachment_mode.md) | The NET_RX_FRAGMENT_BUFFER_ATTACHMENT_MODE enumeration identifies how the operating system should pre-attach NET_PACKET_FRAGMENT buffers to NET_PACKETs for a net adapter client driver's receive queues. |
