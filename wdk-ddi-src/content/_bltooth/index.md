---
UID: TP:bltooth
ms.assetid: a24d2124-fb4a-3c14-aeb8-83c46e9ed71c
ms.author: windowsdriverdev
ms.date: 05/01/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Bluetooth



Overview of the Bluetooth technology.

To develop Bluetooth, you need these headers:

 * [bthddi.h](..\bthddi\index.md)
 * [bthioctl.h](..\bthioctl\index.md)
 * [bthsdpddi.h](..\bthsdpddi\index.md)
 * [bthxddi.h](..\bthxddi\index.md)
 * [sdplib.h](..\sdplib\index.md)
 * [sdpnode.h](..\sdpnode\index.md)

For the programming guide, see [Bluetooth](https://docs.microsoft.com/en-us/windows-hardware/drivers/bluetooth).

## Functions

| Title   | Description   |
| ---- |:---- |
| [SdpAddAttributeToTree function](..\sdplib\nf-sdplib-sdpaddattributetotree.md) | The Bluetooth SdpAddAttributeToTree function is used to attach an SDP attribute node to the top level of an SDP record. |
| [SdpAppendNodeToContainerNode function](..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md) | The Bluetooth SdpAppendNodeToContainerNode function is used to attach an SDP node to a sequence or alternative SDP node. |
| [SdpCreateNodeAlternative function](..\sdplib\nf-sdplib-sdpcreatenodealternative.md) | The Bluetooth SdpCreateNodeAlternative function is used to create an empty alternative sequence SDP node. |
| [SdpCreateNodeBoolean function](..\sdplib\nf-sdplib-sdpcreatenodeboolean.md) | The Bluetooth SdpCreateNodeBoolean function is used to allocate and initialize an SDP_NODE structure to a Boolean type. |
| [SdpCreateNodeInt128 function](..\sdplib\nf-sdplib-sdpcreatenodeint128.md) | The Bluetooth SdpCreateNodeInt128 function is used to allocate and initialize an SDP_NODE structure to a 128-bit integer type. |
| [SdpCreateNodeInt16 function](..\sdplib\nf-sdplib-sdpcreatenodeint16.md) | The Bluetooth SdpCreateNodeInt16 function is used to allocate and initialize an SDP_NODE structure to a 16-bit integer type. |
| [SdpCreateNodeInt32 function](..\sdplib\nf-sdplib-sdpcreatenodeint32.md) | The Bluetooth SdpCreateNodeInt32 function is used to allocate and initialize an SDP_NODE structure to a 32-bit integer type. |
| [SdpCreateNodeInt64 function](..\sdplib\nf-sdplib-sdpcreatenodeint64.md) | The Bluetooth SdpCreateNodeInt64 function is used to allocate and initialize an SDP_NODE structure to a 64-bit integer type. |
| [SdpCreateNodeInt8 function](..\sdplib\nf-sdplib-sdpcreatenodeint8.md) | The Bluetooth SdpCreateNodeInt8 function is used to allocate and initialize an SDP_NODE structure to an 8-bit integer type. |
| [SdpCreateNodeNil function](..\sdplib\nf-sdplib-sdpcreatenodenil.md) | The Bluetooth SdpCreateNodeNil function is used to allocate and initialize an SDP_NODE structure to an empty node type. |
| [SdpCreateNodeSequence function](..\sdplib\nf-sdplib-sdpcreatenodesequence.md) | The Bluetooth SdpCreateNodeSequence function is used to create an empty sequence SDP node. |
| [SdpCreateNodeString function](..\sdplib\nf-sdplib-sdpcreatenodestring.md) | The Bluetooth SdpCreateNodeString function is used to allocate and initialize an SDP_NODE structure to a string type. |
| [SdpCreateNodeTree function](..\sdplib\nf-sdplib-sdpcreatenodetree.md) | The Bluetooth SdpCreateNodeTree function is used to allocate an empty root SDP_TREE_ROOT_NODE structure. |
| [SdpCreateNodeUInt128 function](..\sdplib\nf-sdplib-sdpcreatenodeuint128.md) | The Bluetooth SdpCreateNodeUInt128 function is used to allocate and initialize an SDP_NODE structure to an unsigned 128-bit integer type. |
| [SdpCreateNodeUInt16 function](..\sdplib\nf-sdplib-sdpcreatenodeuint16.md) | The Bluetooth SdpCreateNodeUInt16 function is used to allocate and initialize an SDP_NODE structure to an unsigned 16-bit integer type. |
| [SdpCreateNodeUInt32 function](..\sdplib\nf-sdplib-sdpcreatenodeuint32.md) | The Bluetooth SdpCreateNodeUInt32 function is used to allocate and initialize an SDP_NODE structure to an unsigned 32-bit integer type. |
| [SdpCreateNodeUInt64 function](..\sdplib\nf-sdplib-sdpcreatenodeuint64.md) | The Bluetooth SdpCreateNodeUInt64 function is used to allocate and initialize an SDP_NODE structure to an unsigned 64-bit integer type. |
| [SdpCreateNodeUInt8 function](..\sdplib\nf-sdplib-sdpcreatenodeuint8.md) | The Bluetooth SdpCreateNodeUInt8 function is used to allocate and initialize an SDP_NODE structure to an unsigned 8-bit integer type. |
| [SdpCreateNodeUUID128 function](..\sdplib\nf-sdplib-sdpcreatenodeuuid128.md) | The Bluetooth SdpCreateNodeUUID128 function is used to allocate and initialize an SDP_NODE structure to a 128-bit UUID type. |
| [SdpCreateNodeUUID16 function](..\sdplib\nf-sdplib-sdpcreatenodeuuid16.md) | The Bluetooth SdpCreateNodeUUID16 function is used to allocate and initialize an SDP_NODE structure to a 16-bit UUID type. |
| [SdpCreateNodeUUID32 function](..\sdplib\nf-sdplib-sdpcreatenodeuuid32.md) | The Bluetooth SdpCreateNodeUUID32 function is used to allocate and initialize an SDP_NODE structure to a 32-bit UUID type. |
| [SdpCreateNodeUrl function](..\sdplib\nf-sdplib-sdpcreatenodeurl.md) | The Bluetooth SdpCreateNodeUrl function is used to allocate and initialize an SDP_NODE structure to a URL type. |
| [SdpFindAttributeInTree function](..\sdplib\nf-sdplib-sdpfindattributeintree.md) | The Bluetooth SdpFindAttributeInTree function is used to locate the specified attribute node in the tree-based representation of an SDP record. |
| [SdpFreeTree function](..\sdplib\nf-sdplib-sdpfreetree.md) | The Bluetooth SdpFreeTree function is used to free the memory allocated for the tree-based representation of an SDP record. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PBYTESWAPUINT128 callback](..\bthsdpddi\nc-bthsdpddi-pbyteswapuint128.md) | The Bluetooth SdpByteSwapUint128 function is used to reverse the byte order of an unsigned 128-bit integer. |
| [PBYTESWAPUINT64 callback](..\bthsdpddi\nc-bthsdpddi-pbyteswapuint64.md) | The Bluetooth SdpByteSwapUint64 function is used to reverse the byte order of an unsigned 64-bit integer. |
| [PBYTESWAPUUID128 callback](..\bthsdpddi\nc-bthsdpddi-pbyteswapuuid128.md) | The Bluetooth SdpByteSwapUuid128 function is used to reverse the byte order of a 128-bit universally unique identifier (UUID). |
| [PCONVERTSTREAMTOTREE callback](..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md) | The Bluetooth SdpConvertStreamToTree function is used to create a Microsoft proprietary tree-based representation of an SDP record, while leaving the original stream-based representation unmodified. |
| [PCONVERTTREETOSTREAM callback](..\bthsdpddi\nc-bthsdpddi-pconverttreetostream.md) | The Bluetooth SdpConvertTreeToStream function is used to produce a raw bytestream representation of an SDP record from a tree representation. The raw bytestream version is suitable for publication on a local SDP server. |
| [PFNBTHPORT_INDICATION_CALLBACK callback](..\bthddi\nc-bthddi-pfnbthport_indication_callback.md) | Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and any changes to the status of a currently open L2CAP connection. |
| [PFNBTHPORT_INDICATION_CALLBACK_ENHANCED callback](..\bthddi\nc-bthddi-pfnbthport_indication_callback_enhanced.md) | Profile drivers implement an enhanced L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about any changes to the status of a currently open L2CAP or eL2CAP connection. |
| [PFNBTH_ALLOCATE_BRB callback](..\bthddi\nc-bthddi-pfnbth_allocate_brb.md) | The BthAllocateBrb function allocates a Bluetooth request block (BRB) of the specified type. |
| [PFNBTH_FREE_BRB callback](..\bthddi\nc-bthddi-pfnbth_free_brb.md) | The BthFreeBrb function frees a Bluetooth request block (BRB) that was allocated previously with BthAllocateBrb. |
| [PFNBTH_INITIALIZE_BRB callback](..\bthddi\nc-bthddi-pfnbth_initialize_brb.md) | The BthInitializeBrb function initializes a Bluetooth request block (BRB) allocated on the local stack. |
| [PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE callback](..\bthddi\nc-bthddi-pfnbth_is_bluetooth_version_available.md) | The IsBluetoothVersionAvailable function checks whether a given Bluetooth version is supported by the operating system. |
| [PFNBTH_REUSE_BRB callback](..\bthddi\nc-bthddi-pfnbth_reuse_brb.md) | The BthReuseBrb function reinitializes a Bluetooth request block (BRB) to be reused. |
| [PFNSCO_INDICATION_CALLBACK callback](..\bthddi\nc-bthddi-pfnsco_indication_callback.md) | Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any changes to the status of a currently open SCO connection. |
| [PGETNEXTELEMENT callback](..\bthsdpddi\nc-bthsdpddi-pgetnextelement.md) | The Bluetooth SdpGetNextElement function is used to iterate through the entries found in an SDP record stream. |
| [PRETRIEVEUINT64 callback](..\bthsdpddi\nc-bthsdpddi-pretrieveuint64.md) | The Bluetooth SdpRetrieveUint128 function is used to copy an unaligned 128-bit integer from an SDP stream. |
| [PRETRIEVEUUID128 callback](..\bthsdpddi\nc-bthsdpddi-pretrieveuuid128.md) | The Bluetooth SdpRetrieveUuid128 function is used to copy an unaligned 128-bit universally unique identifier (UUID) from an SDP stream. |
| [PVALIDATESTREAM callback](..\bthsdpddi\nc-bthsdpddi-pvalidatestream.md) | The Bluetooth SdpValidateStream function is used to parse a raw SDP record and determine if it contains errors. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_BASEBAND_CHANNEL_INFO structure](..\bthddi\ns-bthddi-_baseband_channel_info.md) | The BASEBAND_CHANNEL_INFO structure describes output information about the baseband channel that is used by a SCO link after a BRB_GET_CHANNEL_INFO BRB completes. |
| [_BRB structure](..\bthddi\ns-bthddi-_brb.md) | Profile drivers use Bluetooth request blocks (BRBs), to send requests to the Bluetooth driver stack. The BRB structure defines the format for all supported commands that can be sent to a Bluetooth device. |
| [_BRB_ACL_ENTER_ACTIVE_MODE structure](..\bthddi\ns-bthddi-_brb_acl_enter_active_mode.md) | The _BRB_ACL_ENTER_ACTIVE_MODE structure specifies the remote device to be placed into active mode. |
| [_BRB_ACL_GET_MODE structure](..\bthddi\ns-bthddi-_brb_acl_get_mode.md) | The _BRB_ACL_GET_MODE structure describes the ACL mode for the specified remote device. |
| [_BRB_GET_DEVICE_INTERFACE_STRING structure](..\bthddi\ns-bthddi-_brb_get_device_interface_string.md) | The _BRB_GET_DEVICE_INTERFACE_STRING structure describes the device interface string for the current device object. |
| [_BRB_GET_LOCAL_BD_ADDR structure](..\bthddi\ns-bthddi-_brb_get_local_bd_addr.md) | The _BRB_GET_LOCAL_BD_ADDR structure describes the address of the local radio. |
| [_BRB_HEADER structure](..\bthddi\ns-bthddi-_brb_header.md) | The BRB_HEADER structure contains header information about a Bluetooth request block (BRB), including information about the BRB type that the Bluetooth driver stack uses to determine which kind of BRB type to process. |
| [_BRB_L2CA_ACL_TRANSFER structure](..\bthddi\ns-bthddi-_brb_l2ca_acl_transfer.md) | The _BRB_L2CA_ACL_TRANSFER structure describes a buffer to read asynchronous data from, or write asynchronous data to a L2CAP channel. |
| [_BRB_L2CA_CLOSE_CHANNEL structure](..\bthddi\ns-bthddi-_brb_l2ca_close_channel.md) | The _BRB_L2CA_CLOSE_CHANNEL structure describes an open L2CAP channel to close. |
| [_BRB_L2CA_OPEN_CHANNEL structure](..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md) | The _BRB_L2CA_OPEN_CHANNEL structure describes a L2CAP channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming L2CAP connection request that was initiated by a remote device. |
| [_BRB_L2CA_OPEN_ENHANCED_CHANNEL structure](..\bthddi\ns-bthddi-_brb_l2ca_open_enhanced_channel.md) | The _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure is used to open an enhanced L2CAP channel to a remote device, or send a response for accepting/rejecting an incoming enhanced L2CAP connection request that was initiated by a remote device. |
| [_BRB_L2CA_PING structure](..\bthddi\ns-bthddi-_brb_l2ca_ping.md) | The _BRB_L2CA_PING structure describes a request to ping a remote radio. |
| [_BRB_L2CA_REGISTER_SERVER structure](..\bthddi\ns-bthddi-_brb_l2ca_register_server.md) | A profile driver uses the _BRB_L2CA_REGISTER_SERVER structure to register itself as a server capable of receiving L2CAP connections from remote Bluetooth devices. |
| [_BRB_L2CA_UNREGISTER_SERVER structure](..\bthddi\ns-bthddi-_brb_l2ca_unregister_server.md) | A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving L2CAP connections from remote Bluetooth devices. |
| [_BRB_L2CA_UPDATE_CHANNEL structure](..\bthddi\ns-bthddi-_brb_l2ca_update_channel.md) | The _BRB_L2CA_UPDATE_CHANNEL structure describes an update to the link characteristics of an open L2CAP channel to a remote device or to ascertain when certain channel attributes have changed. |
| [_BRB_PSM structure](..\bthddi\ns-bthddi-_brb_psm.md) | The _BRB_PSM structure describes a Protocol/Service Multiplexer (PSM) to register or unregister. |
| [_BRB_SCO_CLOSE_CHANNEL structure](..\bthddi\ns-bthddi-_brb_sco_close_channel.md) | The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close. |
| [_BRB_SCO_FLUSH_CHANNEL structure](..\bthddi\ns-bthddi-_brb_sco_flush_channel.md) | The _BRB_SCO_FLUSH_CHANNEL structure describes a flush operation for a SCO channel. |
| [_BRB_SCO_GET_CHANNEL_INFO structure](..\bthddi\ns-bthddi-_brb_sco_get_channel_info.md) | The _BRB_SCO_GET_CHANNEL_INFO structure describes the settings and statistics of a SCO channel. |
| [_BRB_SCO_GET_SYSTEM_INFO structure](..\bthddi\ns-bthddi-_brb_sco_get_system_info.md) | The _BRB_SCO_GET_SYSTEM_INFO structure describes information about the local system's support for SCO connections. |
| [_BRB_SCO_OPEN_CHANNEL structure](..\bthddi\ns-bthddi-_brb_sco_open_channel.md) | The _BRB_SCO_OPEN_CHANNEL structure describes a SCO channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming SCO connection request that was initiated by a remote device. |
| [_BRB_SCO_REGISTER_SERVER structure](..\bthddi\ns-bthddi-_brb_sco_register_server.md) | A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable of receiving SCO connections from remote Bluetooth devices. |
| [_BRB_SCO_TRANSFER structure](..\bthddi\ns-bthddi-_brb_sco_transfer.md) | The _BRB_SCO_TRANSFER structure describes a buffer to read isochronous data from, or write isochronous data to a SCO channel. |
| [_BRB_SCO_UNREGISTER_SERVER structure](..\bthddi\ns-bthddi-_brb_sco_unregister_server.md) | A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving SCO connections from remote Bluetooth devices. |
| [_BTHDDI_SDP_NODE_INTERFACE structure](..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md) | The BTHDDI_SDP_NODE_INTERFACE structure provides functions for manipulating SDP records, including converting them to and from a tree representation that profile drivers can more easily parse. |
| [_BTHDDI_SDP_PARSE_INTERFACE structure](..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md) | The BTHDDI_SDP_PARSE_INTERFACE structure provides functions for parsing SDP records. |
| [_BTHX_CAPABILITIES structure](..\bthxddi\ns-bthxddi-_bthx_capabilities.md) | The BTHX_CAPABILITIES structure describes the capabilities of the Bluetooth Extensible Transport Driver. |
| [_BTHX_HCI_READ_WRITE_CONTEXT structure](..\bthxddi\ns-bthxddi-_bthx_hci_read_write_context.md) | The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs. |
| [_BTHX_VERSION structure](..\bthxddi\ns-bthxddi-_bthx_version.md) | The BTHX_VERSION structure describes the version or versions that the transport driver supports. |
| [_BTH_COMMAND_HEADER structure](..\bthioctl\ns-bthioctl-_bth_command_header.md) | The BTH_COMMAND_HEADER structure specifies header information for a vendor-specific HCI command. |
| [_BTH_DEVICE_INFO_LIST structure](..\bthioctl\ns-bthioctl-_bth_device_info_list.md) | The BTH_DEVICE_INFO_LIST structure contains output information about all cached, previously discovered remote devices. |
| [_BTH_ENUMERATOR_INFO structure](..\bthddi\ns-bthddi-_bth_enumerator_info.md) | The BTH_ENUMERATOR_INFO structure contains information about an underlying device and the service that caused the Plug and Play (PnP) manager to load the profile driver. |
| [_BTH_LOCAL_RADIO_INFO structure](..\bthioctl\ns-bthioctl-_bth_local_radio_info.md) | The BTH_LOCAL_RADIO_INFO structure contains information about the local Bluetooth system and radio. |
| [_BTH_PROFILE_DRIVER_INTERFACE structure](..\bthddi\ns-bthddi-_bth_profile_driver_interface.md) | The BTH_PROFILE_DRIVER_INTERFACE structure provides functions to allocate, free, initialize, and reuse BRBs, and to determine the currently installed Bluetooth version. |
| [_BTH_RADIO_INFO structure](..\bthioctl\ns-bthioctl-_bth_radio_info.md) | The BTH_RADIO_INFO structure contains information about a remote radio. |
| [_BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure](..\bthioctl\ns-bthioctl-_bth_sdp_attribute_search_request.md) | The BTH_SDP_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to an SDP attribute search. |
| [_BTH_SDP_CONNECT structure](..\bthioctl\ns-bthioctl-_bth_sdp_connect.md) | The BTH_SDP_CONNECT structure contains input and output information about a connection between the local Bluetooth system and a remote SDP server. This structure is passed as the input buffer and output buffer of IOCTL_BTH_SDP_CONNECT. |
| [_BTH_SDP_DISCONNECT structure](..\bthioctl\ns-bthioctl-_bth_sdp_disconnect.md) | The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote SDP connection to terminate. This structure is passed as the input buffer of IOCTL_BTH_SDP_DISCONNECT. |
| [_BTH_SDP_RECORD structure](..\bthioctl\ns-bthioctl-_bth_sdp_record.md) | The BTH_SDP_RECORD structure contains information about an SDP record that is to be added to the local SDP server. |
| [_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure](..\bthioctl\ns-bthioctl-_bth_sdp_service_attribute_search_request.md) | The BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to a combined SDP service and attribute search. This structure is passed as the input buffer to the IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH IOCTL. |
| [_BTH_SDP_SERVICE_SEARCH_REQUEST structure](..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md) | The BTH_SDP_SERVICE_SEARCH_REQUEST structure contains information pertinent to an SDP service search. |
| [_BTH_SDP_STREAM_RESPONSE structure](..\bthioctl\ns-bthioctl-_bth_sdp_stream_response.md) | The BTH_SDP_STREAM_RESPONSE structure contains information about an SDP record. |
| [_BTH_VENDOR_EVENT_INFO structure](..\bthioctl\ns-bthioctl-_bth_vendor_event_info.md) | The BTH_VENDOR_EVENT_INFO structure specifies the buffer that is associated with the GUID_BLUETOOTH_HCI_VENDOR_EVENT GUID. |
| [_BTH_VENDOR_PATTERN structure](..\bthioctl\ns-bthioctl-_bth_vendor_pattern.md) | The BTH_VENDOR_PATTERN structure specifies a vendor pattern. |
| [_BTH_VENDOR_SPECIFIC_COMMAND structure](..\bthioctl\ns-bthioctl-_bth_vendor_specific_command.md) | The BTH_VENDOR_SPECIFIC_COMMAND structure specifies a Bluetooth vendor-specific command. |
| [_CHANNEL_CONFIG_PARAMETERS structure](..\bthddi\ns-bthddi-_channel_config_parameters.md) | The CHANNEL_CONFIG_PARAMETERS structure contains configuration parameters for inbound and outbound directions of a L2CAP channel. |
| [_CHANNEL_CONFIG_PARAMETERS_ENHANCED structure](..\bthddi\ns-bthddi-_channel_config_parameters_enhanced.md) | The CHANNEL_CONFIG_PARAMETERS_ENHANCED structure describes configuration parameters for inbound and outbound directions of an L2CAP channel. |
| [_CHANNEL_CONFIG_RESULTS structure](..\bthddi\ns-bthddi-_channel_config_results.md) | The CHANNEL_CONFIG_RESULTS structure contains configuration parameters and the buffer size of any extra options for the inbound and outbound directions of a L2CAP channel. |
| [_CHANNEL_CONFIG_RESULTS_ENHANCED structure](..\bthddi\ns-bthddi-_channel_config_results_enhanced.md) | The CHANNEL_CONFIG_RESULTS_ENHANCED structure describes configuration parameters and the buffer size of any extra option for the inbound and outbound directions of an L2CAP channel. |
| [_CO_HEADER structure](..\bthddi\ns-bthddi-_co_header.md) | The CO_HEADER structure is used to specify values for the Header member of the L2CAP_CONFIG_OPTION structure. |
| [_INDICATION_PARAMETERS structure](..\bthddi\ns-bthddi-_indication_parameters.md) | The INDICATION_PARAMETERS structure is passed as the Parameters parameter to a profile driver's L2CAP Callback Function. |
| [_INDICATION_PARAMETERS_ENHANCED structure](..\bthddi\ns-bthddi-_indication_parameters_enhanced.md) | The INDICATION_PARAMETERS_ENHANCED structure is passed as the Parameters parameter to a profile driver's enhanced L2CAP Callback Function. |
| [_L2CAP_CONFIG_OPTION structure](..\bthddi\ns-bthddi-_l2cap_config_option.md) | An array of L2CAP_CONFIG_OPTION structures is used to specify values for the ExtraOptions member of the CHANNEL_CONFIG_PARAMETERS, _BRB_L2CA_OPEN_CHANNEL, and INDICATION_PARAMETERS structures. |
| [_L2CAP_CONFIG_RANGE structure](..\bthddi\ns-bthddi-_l2cap_config_range.md) | The L2CAP_CONFIG_RANGE structure is used to specify a range of possible values for the FlushTO member of the _BRB_L2CA_OPEN_CHANNEL structure during incoming requests. |
| [_L2CAP_CONFIG_VALUE_RANGE structure](..\bthddi\ns-bthddi-_l2cap_config_value_range.md) | The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the Mtu and FlushTO members of the _BRB_L2CA_OPEN_CHANNEL structure. |
| [_L2CAP_EXTENDED_FLOW_SPEC structure](..\bthddi\ns-bthddi-_l2cap_extended_flow_spec.md) | The L2CAP_EXTENDED_FLOW_SPEC is reserved for future use. |
| [_L2CAP_FLOWSPEC structure](..\bthddi\ns-bthddi-_l2cap_flowspec.md) | This structure reserved for future use. |
| [_L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure](..\bthddi\ns-bthddi-_l2cap_retransmission_and_flow_control.md) | The L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure describes configuration parameters for enhanced retransmission mode and streaming mode. |
| [_SCO_INDICATION_PARAMETERS structure](..\bthddi\ns-bthddi-_sco_indication_parameters.md) | The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification. |
| [_SDP_NODE structure](..\sdpnode\ns-sdpnode-_sdp_node.md) | The SDP_NODE structure holds information about an element in a tree-based representation of an SDP record. |
| [_SDP_NODE_DATA structure](..\sdpnode\ns-sdpnode-_sdp_node_data.md) | The SDP_NODE_DATA union holds the data of an element in a tree-based representation of an SDP record. |
| [_SDP_NODE_HEADER structure](..\sdpnode\ns-sdpnode-_sdp_node_header.md) | The SDP_NODE_HEADER structure holds information about an element in a tree-based representation of an SDP record. |
| [_SDP_TREE_ROOT_NODE structure](..\sdpnode\ns-sdpnode-_sdp_tree_root_node.md) | The SDP_TREE_ROOT_NODE structure is the root element of a tree-based representation of an SDP record. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_ACL_MODE enumeration](..\bthddi\ne-bthddi-_acl_mode.md) | The ACL_MODE enumeration type is used to list the possible states of an ACL connection. |
| [_BRB_TYPE enumeration](..\bthddi\ne-bthddi-_brb_type.md) | The BRB_TYPE enumeration type is used to determine the Bluetooth request block when a profile driver builds and sends a BRB. |
| [_BRB_VERSION enumeration](..\bthddi\ne-bthddi-_brb_version.md) | Reserved for internal use. |
| [_BTHX_HCI_PACKET_TYPE enumeration](..\bthxddi\ne-bthxddi-_bthx_hci_packet_type.md) | The BTHX_HCI_PACKET_TYPE enumeration lists the different types of packets being sent from the Bluetooth stack to the transport driver. |
| [_BTHX_SCO_SUPPORT enumeration](..\bthxddi\ne-bthxddi-_bthx_sco_support.md) | The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver. |
| [_CODING_FORMAT enumeration](..\bthddi\ne-bthddi-_coding_format.md) | This enumeration is for internal use only. |
| [_ENUMERATOR_ACTION enumeration](..\bthddi\ne-bthddi-_enumerator_action.md) | Reserved for internal use. |
| [_ENUMERATOR_TYPE enumeration](..\bthddi\ne-bthddi-_enumerator_type.md) | The ENUMERATOR_TYPE enumeration type is used to determine whether the enumerated device is associated with a service or a protocol. The ENUMERATOR_TYPE enumeration is intended for internal use only and should not be used by profile drivers. |
| [_INDICATION_CODE enumeration](..\bthddi\ne-bthddi-_indication_code.md) | The INDICATION_CODE enumeration type indicates to a profile driver what type of L2CAP event has occurred. |
| [_L2CAP_DISCONNECT_REASON enumeration](..\bthddi\ne-bthddi-_l2cap_disconnect_reason.md) | The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been disconnected. |
| [_PCM_DATA_FORMAT enumeration](..\bthddi\ne-bthddi-_pcm_data_format.md) | This enumeration is for internal use only. |
| [_SCO_DISCONNECT_REASON enumeration](..\bthddi\ne-bthddi-_sco_disconnect_reason.md) | The SCO_DISCONNECT_REASON enumeration type gives the reason an SCO channel has been disconnected. |
| [_SCO_INDICATION_CODE enumeration](..\bthddi\ne-bthddi-_sco_indication_code.md) | The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding state change. The Bluetooth driver stack passes a value from this enumeration in the Indication argument of a profile driver's SCO Callback Function. |
| [_SCO_LINK_TYPE enumeration](..\bthddi\ne-bthddi-_sco_link_type.md) | The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a ScoIndicationRemoteConnect indication event is processed. |
| [_SCO_RETRANSMISSION_EFFORT enumeration](..\bthddi\ne-bthddi-_sco_retransmission_effort.md) | The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a SCO channel. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_BTHX_GET_VERSION IOCTL](..\bthxddi\ni-bthxddi-ioctl_bthx_get_version.md) | Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver. |
| [IOCTL_BTHX_QUERY_CAPABILITIES IOCTL](..\bthxddi\ni-bthxddi-ioctl_bthx_query_capabilities.md) | IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver. |
| [IOCTL_BTHX_READ_HCI IOCTL](..\bthxddi\ni-bthxddi-ioctl_bthx_read_hci.md) | IOCTL_BTHX_READ_HCI is used to read Bluetooth ACL Data and Events from the transport layer. |
| [IOCTL_BTHX_SET_VERSION IOCTL](..\bthxddi\ni-bthxddi-ioctl_bthx_set_version.md) | IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used. |
| [IOCTL_BTHX_WRITE_HCI IOCTL](..\bthxddi\ni-bthxddi-ioctl_bthx_write_hci.md) | IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer. |
| [IOCTL_BTH_DISCONNECT_DEVICE IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_disconnect_device.md) | Profile drivers use IOCTL_BTH_DISCONNECT_DEVICE to request the operating system to disconnect the specified remote device. |
| [IOCTL_BTH_GET_DEVICE_INFO IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_get_device_info.md) | The IOCTL_BTH_GET_DEVICE_INFO request returns information about all cached, previously discovered remote radios that are Bluetooth-enabled. |
| [IOCTL_BTH_GET_LOCAL_INFO IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_get_local_info.md) | The IOCTL_BTH_GET_LOCAL_INFO request returns information about the local Bluetooth system and radio. |
| [IOCTL_BTH_GET_RADIO_INFO IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_get_radio_info.md) | The IOCTL_BTH_GET_RADIO_INFO request obtains information about the specified remote radio. |
| [IOCTL_BTH_HCI_VENDOR_COMMAND IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_hci_vendor_command.md) | The IOCTL_BTH_HCI_VENDOR_COMMAND request allows Bluetooth applications to send vendor-specific commands to radios. |
| [IOCTL_BTH_SDP_ATTRIBUTE_SEARCH IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_attribute_search.md) | The IOCTL_BTH_SDP_ATTRIBUTE_SEARCH request obtains attributes for the specified SDP record. |
| [IOCTL_BTH_SDP_CONNECT IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md) | The IOCTL_BTH_SDP_CONNECT request creates a connection to the SDP service on a remote Bluetooth device. |
| [IOCTL_BTH_SDP_DISCONNECT IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_disconnect.md) | The IOCTL_BTH_SDP_DISCONNECT request closes a connection to a remote SDP server. |
| [IOCTL_BTH_SDP_REMOVE_RECORD IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_remove_record.md) | The IOCTL_BTH_SDP_REMOVE_RECORD request removes a local SDP record that the profile driver previously submitted. The local server will no longer offer this record to remote devices. |
| [IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_attribute_search.md) | The IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH request combines an SDP service and attribute search into a single operation. This allows a caller to directly obtain SDP records from a remote device. |
| [IOCTL_BTH_SDP_SERVICE_SEARCH IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_service_search.md) | The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to SDP records of a particular service class or classes. |
| [IOCTL_BTH_SDP_SUBMIT_RECORD IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record.md) | The IOCTL_BTH_SDP_SUBMIT_RECORD request allows a profile driver to add an SDP record to the local SDP server, allowing the client to advertise that a service is available on the local computer. |
| [IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO IOCTL](..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md) | The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along with attributes that are not part of the SDP record itself. |
| [IOCTL_INTERNAL_BTHENUM_GET_DEVINFO IOCTL](..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_devinfo.md) | The IOCTL_INTERNAL_BTHENUM_GET_DEVINFO request returns information about the remote device that caused the Plug and Play (PnP) manager to load the current instance of the profile driver. |
| [IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO IOCTL](..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_enuminfo.md) | The IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO request obtains information about the underlying device and service that caused the Plug and Play (PnP) manager to load the profile driver. |
| [IOCTL_INTERNAL_BTH_SUBMIT_BRB IOCTL](..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md) | Profile drivers use IOCTL_INTERNAL_BTH_SUBMIT_BRB to submit a Bluetooth Request Block (BRB) to the Bluetooth driver stack. |
