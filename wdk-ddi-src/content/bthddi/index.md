---
UID: NA:bthddi
ms.assetid: 075c7427-63f8-368d-8e29-b03b091fac0d
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Bthddi.h header



This header is used by Bluetooth. For more information, see
- [Bluetooth](../_bltooth/index.md)

Bthddi.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFNBTHPORT_INDICATION_CALLBACK callback](nc-bthddi-pfnbthport_indication_callback.md) | Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and any changes to the status of a currently open L2CAP connection. |
| [PFNBTHPORT_INDICATION_CALLBACK_ENHANCED callback](nc-bthddi-pfnbthport_indication_callback_enhanced.md) | Profile drivers implement an enhanced L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about any changes to the status of a currently open L2CAP or eL2CAP connection. |
| [PFNBTH_ALLOCATE_BRB callback](nc-bthddi-pfnbth_allocate_brb.md) | The BthAllocateBrb function allocates a Bluetooth request block (BRB) of the specified type. |
| [PFNBTH_FREE_BRB callback](nc-bthddi-pfnbth_free_brb.md) | The BthFreeBrb function frees a Bluetooth request block (BRB) that was allocated previously with BthAllocateBrb. |
| [PFNBTH_INITIALIZE_BRB callback](nc-bthddi-pfnbth_initialize_brb.md) | The BthInitializeBrb function initializes a Bluetooth request block (BRB) allocated on the local stack. |
| [PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE callback](nc-bthddi-pfnbth_is_bluetooth_version_available.md) | The IsBluetoothVersionAvailable function checks whether a given Bluetooth version is supported by the operating system. |
| [PFNBTH_REUSE_BRB callback](nc-bthddi-pfnbth_reuse_brb.md) | The BthReuseBrb function reinitializes a Bluetooth request block (BRB) to be reused. |
| [PFNSCO_INDICATION_CALLBACK callback](nc-bthddi-pfnsco_indication_callback.md) | Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any changes to the status of a currently open SCO connection. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_BASEBAND_CHANNEL_INFO structure](ns-bthddi-_baseband_channel_info.md) | The BASEBAND_CHANNEL_INFO structure describes output information about the baseband channel that is used by a SCO link after a BRB_GET_CHANNEL_INFO BRB completes. |
| [_BRB structure](ns-bthddi-_brb.md) | Profile drivers use Bluetooth request blocks (BRBs), to send requests to the Bluetooth driver stack. The BRB structure defines the format for all supported commands that can be sent to a Bluetooth device. |
| [_BRB_ACL_ENTER_ACTIVE_MODE structure](ns-bthddi-_brb_acl_enter_active_mode.md) | The _BRB_ACL_ENTER_ACTIVE_MODE structure specifies the remote device to be placed into active mode. |
| [_BRB_ACL_GET_MODE structure](ns-bthddi-_brb_acl_get_mode.md) | The _BRB_ACL_GET_MODE structure describes the ACL mode for the specified remote device. |
| [_BRB_GET_DEVICE_INTERFACE_STRING structure](ns-bthddi-_brb_get_device_interface_string.md) | The _BRB_GET_DEVICE_INTERFACE_STRING structure describes the device interface string for the current device object. |
| [_BRB_GET_LOCAL_BD_ADDR structure](ns-bthddi-_brb_get_local_bd_addr.md) | The _BRB_GET_LOCAL_BD_ADDR structure describes the address of the local radio. |
| [_BRB_HEADER structure](ns-bthddi-_brb_header.md) | The BRB_HEADER structure contains header information about a Bluetooth request block (BRB), including information about the BRB type that the Bluetooth driver stack uses to determine which kind of BRB type to process. |
| [_BRB_L2CA_ACL_TRANSFER structure](ns-bthddi-_brb_l2ca_acl_transfer.md) | The _BRB_L2CA_ACL_TRANSFER structure describes a buffer to read asynchronous data from, or write asynchronous data to a L2CAP channel. |
| [_BRB_L2CA_CLOSE_CHANNEL structure](ns-bthddi-_brb_l2ca_close_channel.md) | The _BRB_L2CA_CLOSE_CHANNEL structure describes an open L2CAP channel to close. |
| [_BRB_L2CA_OPEN_CHANNEL structure](ns-bthddi-_brb_l2ca_open_channel.md) | The _BRB_L2CA_OPEN_CHANNEL structure describes a L2CAP channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming L2CAP connection request that was initiated by a remote device. |
| [_BRB_L2CA_OPEN_ENHANCED_CHANNEL structure](ns-bthddi-_brb_l2ca_open_enhanced_channel.md) | The _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure is used to open an enhanced L2CAP channel to a remote device, or send a response for accepting/rejecting an incoming enhanced L2CAP connection request that was initiated by a remote device. |
| [_BRB_L2CA_PING structure](ns-bthddi-_brb_l2ca_ping.md) | The _BRB_L2CA_PING structure describes a request to ping a remote radio. |
| [_BRB_L2CA_REGISTER_SERVER structure](ns-bthddi-_brb_l2ca_register_server.md) | A profile driver uses the _BRB_L2CA_REGISTER_SERVER structure to register itself as a server capable of receiving L2CAP connections from remote Bluetooth devices. |
| [_BRB_L2CA_UNREGISTER_SERVER structure](ns-bthddi-_brb_l2ca_unregister_server.md) | A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving L2CAP connections from remote Bluetooth devices. |
| [_BRB_L2CA_UPDATE_CHANNEL structure](ns-bthddi-_brb_l2ca_update_channel.md) | The _BRB_L2CA_UPDATE_CHANNEL structure describes an update to the link characteristics of an open L2CAP channel to a remote device or to ascertain when certain channel attributes have changed. |
| [_BRB_PSM structure](ns-bthddi-_brb_psm.md) | The _BRB_PSM structure describes a Protocol/Service Multiplexer (PSM) to register or unregister. |
| [_BRB_SCO_CLOSE_CHANNEL structure](ns-bthddi-_brb_sco_close_channel.md) | The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close. |
| [_BRB_SCO_FLUSH_CHANNEL structure](ns-bthddi-_brb_sco_flush_channel.md) | The _BRB_SCO_FLUSH_CHANNEL structure describes a flush operation for a SCO channel. |
| [_BRB_SCO_GET_CHANNEL_INFO structure](ns-bthddi-_brb_sco_get_channel_info.md) | The _BRB_SCO_GET_CHANNEL_INFO structure describes the settings and statistics of a SCO channel. |
| [_BRB_SCO_GET_SYSTEM_INFO structure](ns-bthddi-_brb_sco_get_system_info.md) | The _BRB_SCO_GET_SYSTEM_INFO structure describes information about the local system's support for SCO connections. |
| [_BRB_SCO_OPEN_CHANNEL structure](ns-bthddi-_brb_sco_open_channel.md) | The _BRB_SCO_OPEN_CHANNEL structure describes a SCO channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming SCO connection request that was initiated by a remote device. |
| [_BRB_SCO_REGISTER_SERVER structure](ns-bthddi-_brb_sco_register_server.md) | A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable of receiving SCO connections from remote Bluetooth devices. |
| [_BRB_SCO_TRANSFER structure](ns-bthddi-_brb_sco_transfer.md) | The _BRB_SCO_TRANSFER structure describes a buffer to read isochronous data from, or write isochronous data to a SCO channel. |
| [_BRB_SCO_UNREGISTER_SERVER structure](ns-bthddi-_brb_sco_unregister_server.md) | A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving SCO connections from remote Bluetooth devices. |
| [_BTH_ENUMERATOR_INFO structure](ns-bthddi-_bth_enumerator_info.md) | The BTH_ENUMERATOR_INFO structure contains information about an underlying device and the service that caused the Plug and Play (PnP) manager to load the profile driver. |
| [_BTH_PROFILE_DRIVER_INTERFACE structure](ns-bthddi-_bth_profile_driver_interface.md) | The BTH_PROFILE_DRIVER_INTERFACE structure provides functions to allocate, free, initialize, and reuse BRBs, and to determine the currently installed Bluetooth version. |
| [_CHANNEL_CONFIG_PARAMETERS structure](ns-bthddi-_channel_config_parameters.md) | The CHANNEL_CONFIG_PARAMETERS structure contains configuration parameters for inbound and outbound directions of a L2CAP channel. |
| [_CHANNEL_CONFIG_PARAMETERS_ENHANCED structure](ns-bthddi-_channel_config_parameters_enhanced.md) | The CHANNEL_CONFIG_PARAMETERS_ENHANCED structure describes configuration parameters for inbound and outbound directions of an L2CAP channel. |
| [_CHANNEL_CONFIG_RESULTS structure](ns-bthddi-_channel_config_results.md) | The CHANNEL_CONFIG_RESULTS structure contains configuration parameters and the buffer size of any extra options for the inbound and outbound directions of a L2CAP channel. |
| [_CHANNEL_CONFIG_RESULTS_ENHANCED structure](ns-bthddi-_channel_config_results_enhanced.md) | The CHANNEL_CONFIG_RESULTS_ENHANCED structure describes configuration parameters and the buffer size of any extra option for the inbound and outbound directions of an L2CAP channel. |
| [_CO_HEADER structure](ns-bthddi-_co_header.md) | The CO_HEADER structure is used to specify values for the Header member of the L2CAP_CONFIG_OPTION structure. |
| [_INDICATION_PARAMETERS structure](ns-bthddi-_indication_parameters.md) | The INDICATION_PARAMETERS structure is passed as the Parameters parameter to a profile driver's L2CAP Callback Function. |
| [_INDICATION_PARAMETERS_ENHANCED structure](ns-bthddi-_indication_parameters_enhanced.md) | The INDICATION_PARAMETERS_ENHANCED structure is passed as the Parameters parameter to a profile driver's enhanced L2CAP Callback Function. |
| [_L2CAP_CONFIG_OPTION structure](ns-bthddi-_l2cap_config_option.md) | An array of L2CAP_CONFIG_OPTION structures is used to specify values for the ExtraOptions member of the CHANNEL_CONFIG_PARAMETERS, _BRB_L2CA_OPEN_CHANNEL, and INDICATION_PARAMETERS structures. |
| [_L2CAP_CONFIG_RANGE structure](ns-bthddi-_l2cap_config_range.md) | The L2CAP_CONFIG_RANGE structure is used to specify a range of possible values for the FlushTO member of the _BRB_L2CA_OPEN_CHANNEL structure during incoming requests. |
| [_L2CAP_CONFIG_VALUE_RANGE structure](ns-bthddi-_l2cap_config_value_range.md) | The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the Mtu and FlushTO members of the _BRB_L2CA_OPEN_CHANNEL structure. |
| [_L2CAP_EXTENDED_FLOW_SPEC structure](ns-bthddi-_l2cap_extended_flow_spec.md) | The L2CAP_EXTENDED_FLOW_SPEC is reserved for future use. |
| [_L2CAP_FLOWSPEC structure](ns-bthddi-_l2cap_flowspec.md) | This structure reserved for future use. |
| [_L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure](ns-bthddi-_l2cap_retransmission_and_flow_control.md) | The L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure describes configuration parameters for enhanced retransmission mode and streaming mode. |
| [_SCO_INDICATION_PARAMETERS structure](ns-bthddi-_sco_indication_parameters.md) | The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_ACL_MODE enumeration](ne-bthddi-_acl_mode.md) | The ACL_MODE enumeration type is used to list the possible states of an ACL connection. |
| [_BRB_TYPE enumeration](ne-bthddi-_brb_type.md) | The BRB_TYPE enumeration type is used to determine the Bluetooth request block when a profile driver builds and sends a BRB. |
| [_BRB_VERSION enumeration](ne-bthddi-_brb_version.md) | Reserved for internal use. |
| [_CODING_FORMAT enumeration](ne-bthddi-_coding_format.md) | This enumeration is for internal use only. |
| [_ENUMERATOR_ACTION enumeration](ne-bthddi-_enumerator_action.md) | Reserved for internal use. |
| [_ENUMERATOR_TYPE enumeration](ne-bthddi-_enumerator_type.md) | The ENUMERATOR_TYPE enumeration type is used to determine whether the enumerated device is associated with a service or a protocol. The ENUMERATOR_TYPE enumeration is intended for internal use only and should not be used by profile drivers. |
| [_INDICATION_CODE enumeration](ne-bthddi-_indication_code.md) | The INDICATION_CODE enumeration type indicates to a profile driver what type of L2CAP event has occurred. |
| [_L2CAP_DISCONNECT_REASON enumeration](ne-bthddi-_l2cap_disconnect_reason.md) | The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been disconnected. |
| [_PCM_DATA_FORMAT enumeration](ne-bthddi-_pcm_data_format.md) | This enumeration is for internal use only. |
| [_SCO_DISCONNECT_REASON enumeration](ne-bthddi-_sco_disconnect_reason.md) | The SCO_DISCONNECT_REASON enumeration type gives the reason an SCO channel has been disconnected. |
| [_SCO_INDICATION_CODE enumeration](ne-bthddi-_sco_indication_code.md) | The SCO_INDICATION_CODE enumeration type describes the type of an incoming SCO connection or bonding state change. The Bluetooth driver stack passes a value from this enumeration in the Indication argument of a profile driver's SCO Callback Function. |
| [_SCO_LINK_TYPE enumeration](ne-bthddi-_sco_link_type.md) | The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a ScoIndicationRemoteConnect indication event is processed. |
| [_SCO_RETRANSMISSION_EFFORT enumeration](ne-bthddi-_sco_retransmission_effort.md) | The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a SCO channel. |
