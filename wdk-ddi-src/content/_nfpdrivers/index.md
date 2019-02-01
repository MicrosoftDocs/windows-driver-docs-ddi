---
UID: TP:nfpdrivers
ms.assetid: e2a2f925-0a75-3b74-b121-38dab2d236ad
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
-	Windows
---

# Near field communications (NFC)

## -description

Overview of the Near field communications (NFC) technology.

To develop Near field communications (NFC), you need these headers:

 * [nfccx.h](..\nfccx\index.md)
 * [nfccxbugcodes.h](..\nfccxbugcodes\index.md)
 * [nfccxfuncenum.h](..\nfccxfuncenum\index.md)
 * [nfcradiodev.h](..\nfcradiodev\index.md)
 * [nfcsedev.h](..\nfcsedev\index.md)
 * [nfpdev.h](..\nfpdev\index.md)
 * [winsmcrd.h](..\winsmcrd\index.md)

For the programming guide, see [Near field communications (NFC)](https://docs.microsoft.com/windows-hardware/drivers/nfc).

## Functions

| Title   | Description   |
| ---- |:---- |
| [NFC_CX_CLIENT_CONFIG_INIT function](..\nfccx\nf-nfccx-nfc_cx_client_config_init.md) | The NFC_CX_CLIENT_CONFIG_INIT function initializes the NFC_CX_CLIENT_CONFIG structure. |
| [NFC_CX_LLCP_CONFIG_INIT function](..\nfccx\nf-nfccx-nfc_cx_llcp_config_init.md) | The NFC_CX_LLCP_CONFIG_INIT function initializes the NFC_CX_LLCP_CONFIG structure. |
| [NFC_CX_RF_DISCOVERY_CONFIG_INIT function](..\nfccx\nf-nfccx-nfc_cx_rf_discovery_config_init.md) | The NFC_CX_RF_DISCOVERY_CONFIG_INIT function initializes the NFC_CX_RF_DISCOVERY_CONFIG structure. |
| [NfcCxDeviceDeinitialize function](..\nfccx\nf-nfccx-nfccxdevicedeinitialize.md) | Called by the client driver after a WDF device has been created during the AddDevice routine. |
| [NfcCxDeviceInitConfig function](..\nfccx\nf-nfccx-nfccxdeviceinitconfig.md) | Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged |
| [NfcCxDeviceInitialize function](..\nfccx\nf-nfccx-nfccxdeviceinitialize.md) | Called by the client driver after a WDF device has been created during the AddDevice routine. |
| [NfcCxHardwareEvent function](..\nfccx\nf-nfccx-nfccxhardwareevent.md) | Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following |
| [NfcCxNciReadNotification function](..\nfccx\nf-nfccx-nfccxncireadnotification.md) | Called by the client driver when a read packet is available. |
| [NfcCxRegisterSequenceHandler function](..\nfccx\nf-nfccx-nfccxregistersequencehandler.md) | Called by the client driver during initialization to register for handling specific sequences. |
| [NfcCxSetLlcpConfig function](..\nfccx\nf-nfccx-nfccxsetllcpconfig.md) | Called by the client driver to configure the LLCP parameters. |
| [NfcCxSetRfDiscoveryConfig function](..\nfccx\nf-nfccx-nfccxsetrfdiscoveryconfig.md) | Called by the client driver to configure the RF discovery parameters. |
| [NfcCxUnregisterSequenceHandler function](..\nfccx\nf-nfccx-nfccxunregistersequencehandler.md) | Called by the client driver during device shutdown to unregister for the previously registered sequence handler callback. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_NFC_CX_DEVICE_IO_CONTROL callback function](..\nfccx\nc-nfccx-evt_nfc_cx_device_io_control.md) | Called by the NFC CX to send an unhandled IOCTL to the client driver. |
| [EVT_NFC_CX_SEQUENCE_HANDLER callback function](..\nfccx\nc-nfccx-evt_nfc_cx_sequence_handler.md) | Called by the NFC CX to notify the client driver to handle the specific registered sequence. |
| [EVT_NFC_CX_WRITE_NCI_PACKET callback function](..\nfccx\nc-nfccx-evt_nfc_cx_write_nci_packet.md) | Called by the NFC CX to send a write packet to the client driver. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NFCCX_DRIVER_GLOBALS structure](..\nfccx\ns-nfccx-_nfccx_driver_globals.md) | "." |
| [_NFCRM_RADIO_STATE structure](..\nfcradiodev\ns-nfcradiodev-_nfcrm_radio_state.md) | This structure is used to indicate the radio state. |
| [_NFCRM_SET_RADIO_STATE structure](..\nfcradiodev\ns-nfcradiodev-_nfcrm_set_radio_state.md) | This structure is used to set the radio state. The driver, in the case of airplane mode, has to persist the radio state and restore it when airplane mode is disabled. |
| [_NFC_CX_CLIENT_CONFIG structure](..\nfccx\ns-nfccx-_nfc_cx_client_config.md) | The NFC_CX_CLIENT_CONFIG structure is an input parameter to NfcCxDeviceInitConfig. |
| [_NFC_CX_HARDWARE_EVENT structure](..\nfccx\ns-nfccx-_nfc_cx_hardware_event.md) | The NFC_CX_HARDWARE_EVENT structure is an input parameter to NfcCxHardwareEvent. |
| [_NFC_CX_LLCP_CONFIG structure](..\nfccx\ns-nfccx-_nfc_cx_llcp_config.md) | The NFC_CX_LLCP_CONFIG structure is an input parameter to NfcCxSetLlcpConfig. |
| [_NFC_CX_RF_DISCOVERY_CONFIG structure](..\nfccx\ns-nfccx-_nfc_cx_rf_discovery_config.md) | The NFC_CX_RF_DISCOVERY_CONFIG structure contains RF discovery configuration settings. Discovery configuration should be completed during initialization after calling NfcDxDeviceInitialize, otherwise an error is returned. |
| [_SCARD_IO_REQUEST structure](..\winsmcrd\ns-winsmcrd-_scard_io_request.md) | This structure is used to identify a smart card I/O request. |
| [_SECURE_ELEMENT_AID_ROUTING_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_aid_routing_info.md) | SECURE_ELEMENT_AID_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY. |
| [_SECURE_ELEMENT_ENDPOINT_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_endpoint_info.md) | SECURE_ELEMENT_ENDPOINT_INFO is a member of SECURE_ELEMENT_ENDPOINT_LIST. |
| [_SECURE_ELEMENT_ENDPOINT_LIST structure](..\nfcsedev\ns-nfcsedev-_secure_element_endpoint_list.md) | The output parameter for IOCTL_NFCSE_ENUM_ENDPOINTS. |
| [_SECURE_ELEMENT_EVENT_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_event_info.md) | This structure provides information about a secure element event. |
| [_SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_event_subscription_info.md) | The SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure is an input parameter to IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT. |
| [_SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD structure](..\nfcsedev\ns-nfcsedev-_secure_element_hce_activation_payload.md) | "." |
| [_SECURE_ELEMENT_HCE_DATA_PACKET structure](..\nfcsedev\ns-nfcsedev-_secure_element_hce_data_packet.md) | SECURE_ELEMENT_HCE_DATA_PACKET is an input buffer to IOCTL_NFCSE_HCE_REMOTE_SEND and output buffer for IOCTL_NFCSE_HCE_REMOTE_RECV. |
| [_SECURE_ELEMENT_NFCC_CAPABILITIES structure](..\nfcsedev\ns-nfcsedev-_secure_element_nfcc_capabilities.md) | SECURE_ELEMENT_NFCC_CAPABILITIES contains NFC controller capabilities. |
| [_SECURE_ELEMENT_PROTO_ROUTING_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_proto_routing_info.md) | SECURE_ELEMENT_PROTO_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY. |
| [_SECURE_ELEMENT_ROUTING_TABLE structure](..\nfcsedev\ns-nfcsedev-_secure_element_routing_table.md) | SECURE_ELEMENT_ROUTING_TABLE is an input parameter for IOCTL_NFCSE_SET_ROUTING_TABLE. |
| [_SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure](..\nfcsedev\ns-nfcsedev-_secure_element_routing_table_entry.md) | SECURE_ELEMENT_ROUTING_TABLE_ENTRY is a member of SECURE_ELEMENT_ROUTING_TABLE. |
| [_SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_set_card_emulation_mode_info.md) | SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO is the input parameter for IOCTL_NFCSE_SET_CARD_EMULATION_MODE. |
| [_SECURE_ELEMENT_TECH_ROUTING_INFO structure](..\nfcsedev\ns-nfcsedev-_secure_element_tech_routing_info.md) | SECURE_ELEMENT_TECH_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NFC_CX_CE_MODE_CONFIG enumeration](..\nfccx\ne-nfccx-_nfc_cx_ce_mode_config.md) | This enumeration specifies CE listening mode flags. |
| [_NFC_CX_DEVICE_MODE enumeration](..\nfccx\ne-nfccx-_nfc_cx_device_mode.md) | Specifies device mode flags. |
| [_NFC_CX_DRIVER_FLAGS enumeration](..\nfccx\ne-nfccx-_nfc_cx_driver_flags.md) | Specifies run-time driver flags. |
| [_NFC_CX_HOST_ACTION enumeration](..\nfccx\ne-nfccx-_nfc_cx_host_action.md) | The NFC_CX_HOST_ACTION enumeration specifies host actions. |
| [_NFC_CX_NFCIP_MODE_CONFIG enumeration](..\nfccx\ne-nfccx-_nfc_cx_nfcip_mode_config.md) | The NFC_CX_NFCIP_MODE_CONFIG enumeration specifies the NFC-IP initiator mode. |
| [_NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration](..\nfccx\ne-nfccx-_nfc_cx_nfcip_tgt_mode_config.md) | The NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration specifies NFC-IP target mode. |
| [_NFC_CX_POLL_BAILOUT_CONFIG enumeration](..\nfccx\ne-nfccx-_nfc_cx_poll_bailout_config.md) | The NFC_CX_POLL_BAILOUT_CONFIG enumeration specifies poll mode bail out. |
| [_NFC_CX_POLL_MODE_CONFIG enumeration](..\nfccx\ne-nfccx-_nfc_cx_poll_mode_config.md) | The NFC_CX_POLL_MODE_CONFIG enumeration specifies poll mode. |
| [_NFC_CX_SEQUENCE enumeration](..\nfccx\ne-nfccx-_nfc_cx_sequence.md) | The NFC_CX_SEQUENCE enumeration specifies sequences. |
| [_NFC_CX_TRANSPORT_TYPE enumeration](..\nfccx\ne-nfccx-_nfc_cx_transport_type.md) | The NFC_CX_TRANSPORT_TYPE enumeration specifies transport types. |
| [_SECURE_ELEMENT_CARD_EMULATION_MODE enumeration](..\nfcsedev\ne-nfcsedev-_secure_element_card_emulation_mode.md) | This enumeration indicates the card emulation mode of a secure element. |
| [_SECURE_ELEMENT_EVENT_TYPE enumeration](..\nfcsedev\ne-nfcsedev-_secure_element_event_type.md) | Indicates the type of secure element events. |
| [_SECURE_ELEMENT_ROUTING_TYPE enumeration](..\nfcsedev\ne-nfcsedev-_secure_element_routing_type.md) | SECURE_ELEMENT_ROUTING_TYPE is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY. |
| [_SECURE_ELEMENT_TYPE enumeration](..\nfcsedev\ne-nfcsedev-_secure_element_type.md) | Indicates the type of a secure element. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_NFCRM_QUERY_RADIO_STATE IOCTL](..\nfcradiodev\ni-nfcradiodev-ioctl_nfcrm_query_radio_state.md) | This IOCTL is used by the radio management application or service to query the current radio power state of the proximity device. |
| [IOCTL_NFCRM_SET_RADIO_STATE IOCTL](..\nfcradiodev\ni-nfcradiodev-ioctl_nfcrm_set_radio_state.md) | This IOCTL is used by the radio management application or service to set the radio power state of the proximity device. |
| [IOCTL_NFCSERM_QUERY_RADIO_STATE IOCTL](..\nfcradiodev\ni-nfcradiodev-ioctl_nfcserm_query_radio_state.md) | This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device. |
| [IOCTL_NFCSERM_SET_RADIO_STATE IOCTL](..\nfcradiodev\ni-nfcradiodev-ioctl_nfcserm_set_radio_state.md) | This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device. |
| [IOCTL_NFCSE_ENUM_ENDPOINTS IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_enum_endpoints.md) | Returns information regarding the list of all the secure elements attached to the NFC controller. |
| [IOCTL_NFCSE_GET_NEXT_EVENT IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_get_next_event.md) | The IOCTL_NFCSE_GET_NEXT_EVENT control code returns the next event available in the buffer, or if there are no more buffered events remains pending until a secure element event is available. The event details must then be returned to the caller. |
| [IOCTL_NFCSE_GET_NFCC_CAPABILITIES IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_get_nfcc_capabilities.md) | The IOCTL_NFCSE_GET_NFCC_CAPABILITIES control code returns information about the current NFC controller capabilities, including the maximum Listen Mode Routing table size (defined in section 4.2 of the NFC Controller Interface (NCI) Technical Specification Version 1.1) and supported routing modes. |
| [IOCTL_NFCSE_GET_ROUTING_TABLE IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_get_routing_table.md) | Returns information regarding the current configuration of listen mode routing table. |
| [IOCTL_NFCSE_HCE_REMOTE_RECV IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_hce_remote_recv.md) | Either returns the next data buffer available, or if there are no more buffered data, the request shall stay pending until an APDU buffer is available for reading. |
| [IOCTL_NFCSE_HCE_REMOTE_SEND IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_hce_remote_send.md) | Transmits response APDU from DeviceHost NFCEE to remote device. The caller must be sure that response APDU is conformant to ISO-IEC 7816-4. |
| [IOCTL_NFCSE_SET_CARD_EMULATION_MODE IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_set_card_emulation_mode.md) | The IOCTL_NFCSE_SET_CARD_EMULATION_MODE control code sets whether the specified secure element is exposed in card emulation mode. |
| [IOCTL_NFCSE_SET_ROUTING_TABLE IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_set_routing_table.md) | Configures NFC controller listen mode routing table. |
| [IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT IOCTL](..\nfcsedev\ni-nfcsedev-ioctl_nfcse_subscribe_for_event.md) | The IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT control code is issued by a client to subscribe to a specific event. |
| [IOCTL_NFP_DISABLE IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_disable.md) | A client sends the IOCTL_NFP_DISABLE request to temporarily disable subscriptions, publications, and presence events. |
| [IOCTL_NFP_ENABLE IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_enable.md) | The client sends the IOCTL_NFP_ENABLE request to re-enable previously disabled subscriptions, publications, and presence events. |
| [IOCTL_NFP_GET_KILO_BYTES_PER_SECOND IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_get_kilo_bytes_per_second.md) | A client sends the IOCTL_NFP_GET_KILO_BYTES_PER_SECOND request to any generic handle, one that is non-published and non-subscribed, to the provider device. |
| [IOCTL_NFP_GET_MAX_MESSAGE_BYTES IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_get_max_message_bytes.md) | A client sends the IOCTL_NFP_GET_MAX_MESSAGE_BYTES request to any generic handle, one that is non-published and non-subscribed, to the provider device to determine the maximum message size supported. |
| [IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_get_next_subscribed_message.md) | The client sends the IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE request to the subscription handle repeatedly in order to receive subscribed messages as they arrive. |
| [IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_get_next_transmitted_message.md) | A client interested in receiving notifications that a message has been transmitted will send the IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE request to the proximity driver. |
| [IOCTL_NFP_SET_PAYLOAD IOCTL](..\nfpdev\ni-nfpdev-ioctl_nfp_set_payload.md) | A client application sends message data and confirms publication with the IOCTL_NFP_SET_PAYLOAD request. |
| [IOCTL_SMARTCARD_GET_ATTRIBUTE IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_get_attribute.md) | The IOCTL_SMARTCARD_GET_ATTRIBUTE control code queries for smart card attribues. |
| [IOCTL_SMARTCARD_GET_STATE IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_get_state.md) | The IOCTL_SMARTCARD_GET_STATE control code gets the current status of the smart card. |
| [IOCTL_SMARTCARD_IS_ABSENT IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_is_absent.md) | The IOCTL_SMARTCARD_IS_ABSENT control code returns immediately with STATUS_SUCCESS if no smart card is currently detected. |
| [IOCTL_SMARTCARD_IS_PRESENT IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_is_present.md) | The IOCTL_SMARTCARD_IS_PRESENT control code detects whether a smart card is currently detected. |
| [IOCTL_SMARTCARD_POWER IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_power.md) | Windows may require a driver to have this IOCTL to be NOP and return success. |
| [IOCTL_SMARTCARD_SET_ATTRIBUTE IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_set_attribute.md) | The IOCTL_SMARTCARD_SET_ATTRIBUTE control code sets an attribute and returns STATUS_SUCCESS on SCARD_ATTR_DEVICE_IN_USE; otherwise, it returns STATUS_NOT_SUPPORTED. |
| [IOCTL_SMARTCARD_SET_PROTOCOL IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_set_protocol.md) | Sets the procotol the driver communicates to the smart card with after the card is detected. |
| [IOCTL_SMARTCARD_TRANSMIT IOCTL](..\winsmcrd\ni-winsmcrd-ioctl_smartcard_transmit.md) | Transmits data from the client to the detected smart card in ISO7816-4 compliant APDU. |
