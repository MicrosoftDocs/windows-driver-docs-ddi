---
UID: NA:wwan
ms.assetid: 5d64f71a-37de-3e02-bd8a-2f870aefdc5b
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wwan.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Wwan.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [WWAN_IP_CONFIGURATION_FLAGS structure](ns-wwan-wwan_ip_configuration_flags.md) | The WWAN_IP_CONFIGURATION_FLAGS structure represents flags that describe the availability of the IP address, gateway, DNS server, and/or MTU information of a PDP context. |
| [_WWAN_AUTH_AKAP_CHALLENGE structure](ns-wwan-_wwan_auth_akap_challenge.md) | The WWAN_AUTH_AKAP_CHALLENGE structure represents an authentication challenge using the AKA' method. |
| [_WWAN_AUTH_AKAP_RESPONSE structure](ns-wwan-_wwan_auth_akap_response.md) | The WWAN_AUTH_AKAP_RESPONSE structure represents a response to an AKA' (AKA Prime) authentication challenge. |
| [_WWAN_AUTH_AKA_CHALLENGE structure](ns-wwan-_wwan_auth_aka_challenge.md) | The WWAN_AUTH_AKA_CHALLENGE structure represents an authentication challenge using the AKA method. |
| [_WWAN_AUTH_AKA_RESPONSE structure](ns-wwan-_wwan_auth_aka_response.md) | The WWAN_AUTH_AKA_RESPONSE structure represents a response to an AKA authentication challenge. |
| [_WWAN_AUTH_CHALLENGE structure](ns-wwan-_wwan_auth_challenge.md) | The WWAN_AUTH_CHALLENGE structure represents an authentication challenge for a specific method. |
| [_WWAN_AUTH_RESPONSE structure](ns-wwan-_wwan_auth_response.md) | The WWAN_AUTH_RESPONSE structure represents an authentication challenge response. |
| [_WWAN_AUTH_SIM_CHALLENGE structure](ns-wwan-_wwan_auth_sim_challenge.md) | The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method. |
| [_WWAN_AUTH_SIM_RESPONSE structure](ns-wwan-_wwan_auth_sim_response.md) | The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge. |
| [_WWAN_BASE_STATIONS_INFO structure](ns-wwan-_wwan_base_stations_info.md) | The WWAN_BASE_STATIONS_INFO structure represents information about both serving and neighboring base stations. |
| [_WWAN_BASE_STATIONS_INFO_REQ structure](ns-wwan-_wwan_base_stations_info_req.md) | The WWAN_BASE_STATIONS_INFO_REQ structure represents the aspects of cellular base stations information that are requested in a base stations information query. |
| [_WWAN_CDMA_MRL structure](ns-wwan-_wwan_cdma_mrl.md) | The WWAN_CDMA_MRL structure represents the measured results list (MRL) of both serving and neighboring CDMA cells. |
| [_WWAN_CDMA_MRL_INFO structure](ns-wwan-_wwan_cdma_mrl_info.md) | The WWAN_CDMA_MRL_INFO structure represents information about a CDMA serving cell or neighboring cell. |
| [_WWAN_CONTEXT structure](ns-wwan-_wwan_context.md) | The WWAN_CONTEXT structure represents a provisioned context that is supported by the MB device. |
| [_WWAN_CONTEXT_STATE structure](ns-wwan-_wwan_context_state.md) | The WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB device. |
| [_WWAN_DEVICE_CAPS structure](ns-wwan-_wwan_device_caps.md) | The WWAN_DEVICE_CAPS structure represents the capabilities of the MB device. |
| [_WWAN_DEVICE_CAPS_EX structure](ns-wwan-_wwan_device_caps_ex.md) | The WWAN_DEVICE_CAPS_EX structure represents the capabilities of the mobile broadband device. |
| [_WWAN_DEVICE_SERVICE_COMMAND structure](ns-wwan-_wwan_device_service_command.md) | The WWAN_DEVICE_SERVICE_COMMAND structure represents a device service command. |
| [_WWAN_DEVICE_SERVICE_ENTRY structure](ns-wwan-_wwan_device_service_entry.md) | The WWAN_DEVICE_SERVICE_ENTRY structure describes information about a device service. |
| [_WWAN_DEVICE_SERVICE_EVENT structure](ns-wwan-_wwan_device_service_event.md) | The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event. |
| [_WWAN_DEVICE_SERVICE_RESPONSE structure](ns-wwan-_wwan_device_service_response.md) | The WWAN_DEVICE_SERVICE_RESPONSE structure represents a response from a device service. |
| [_WWAN_DEVICE_SERVICE_SESSION structure](ns-wwan-_wwan_device_service_session.md) | The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service. |
| [_WWAN_DEVICE_SERVICE_SESSION_READ structure](ns-wwan-_wwan_device_service_session_read.md) | The WWAN_DEVICE_SERVICE_SESSION_READ structure represents data associated with a device service session read notification. |
| [_WWAN_DEVICE_SERVICE_SESSION_WRITE structure](ns-wwan-_wwan_device_service_session_write.md) | The WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents data associated with a device service session write request. |
| [_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure](ns-wwan-_wwan_device_service_supported_commands.md) | The WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service. |
| [_WWAN_DEVICE_SLOT_MAPPING_INFO structure](ns-wwan-_wwan_device_slot_mapping_info.md) | The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device. |
| [_WWAN_DRIVER_CAPS structure](ns-wwan-_wwan_driver_caps.md) | The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver. |
| [_WWAN_GET_SLOT_INFO structure](ns-wwan-_wwan_get_slot_info.md) | The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for. |
| [_WWAN_GET_VISIBLE_PROVIDERS structure](ns-wwan-_wwan_get_visible_providers.md) | The WWAN_GET_VISIBLE_PROVIDERS structure provides information about the type of visible providers to return. |
| [_WWAN_GSM_NMR structure](ns-wwan-_wwan_gsm_nmr.md) | The WWAN_GSM_NMR structure represents the network measurement report (NMR) of neighboring GSM cells. |
| [_WWAN_GSM_NMR_INFO structure](ns-wwan-_wwan_gsm_nmr_info.md) | The WWAN_GSM_NMR_INFO structure represents information about a neighboring GSM cell. |
| [_WWAN_GSM_SERVING_CELL_INFO structure](ns-wwan-_wwan_gsm_serving_cell_info.md) | The WWAN_GSM_SERVING_CELL_INFO structure represents information about the GSM serving cell. |
| [_WWAN_IPADDRESS_ENTRY structure](ns-wwan-_wwan_ipaddress_entry.md) | The WWAN_IPADDRESS_ENTRY structure represents either the IPV4 or IPV6 address of a PDP context. |
| [_WWAN_IPV4_ADDRESS structure](ns-wwan-_wwan_ipv4_address.md) | The WWAN_IPV4_ADDRESS structure represents an IPV4 address of a PDP context. |
| [_WWAN_IPV6_ADDRESS structure](ns-wwan-_wwan_ipv6_address.md) | The WWAN_IPV6_ADDRESS structure represents an IPV6 address of a PDP context. |
| [_WWAN_IP_ADDRESS_STATE structure](ns-wwan-_wwan_ip_address_state.md) | The WWAN_IP_ADDRESS_STATE structure represents the IP addresses, gateways, DNS servers, and/or MTUs of a PDP context. |
| [_WWAN_LIST_HEADER structure](ns-wwan-_wwan_list_header.md) | The WWAN_LIST_HEADER structure represents the header of a list of MB objects, including the number of objects in the list that follow the header in memory. |
| [_WWAN_LTE_MRL structure](ns-wwan-_wwan_lte_mrl.md) | The WWAN_LTE_MRL structure represents the measured results list (MRL) of neighboring LTE cells. |
| [_WWAN_LTE_MRL_INFO structure](ns-wwan-_wwan_lte_mrl_info.md) | The WWAN_LTE_MRL_INFO structure represents information about a neighboring LTE cell. |
| [_WWAN_LTE_SERVING_CELL_INFO structure](ns-wwan-_wwan_lte_serving_cell_info.md) | The WWAN_LTE_SERVING_CELL_INFO structure represents information about the LTE serving cell. |
| [_WWAN_MODEM_CONFIG_INFO structure](ns-wwan-_wwan_modem_config_info.md) | The WWAN_MODEM_CONFIG_INFO structure represents the modem's configuration information. |
| [_WWAN_MODEM_CONFIG_STATUS structure](ns-wwan-_wwan_modem_config_status.md) | The WWAN_MODEM_CONFIG_STATUS structure represents a modem's configuration (config) status. |
| [_WWAN_NETWORK_IDLE_HINT structure](ns-wwan-_wwan_network_idle_hint.md) | The WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface. |
| [_WWAN_PACKET_SERVICE structure](ns-wwan-_wwan_packet_service.md) | The WWAN_PACKET_SERVICE structure represents the packet service attachment state of the MB device. |
| [_WWAN_PCO_VALUE structure](ns-wwan-_wwan_pco_value.md) | The WWAN_PCO_VALUE structure represents the PCO information payload from the network as defined in the 3GPP TS24.008 spec. |
| [_WWAN_PIN_ACTION structure](ns-wwan-_wwan_pin_action.md) | The WWAN_PIN_ACTION structure represents actions to perform with a Personal Identification Number (PIN). |
| [_WWAN_PIN_DESC structure](ns-wwan-_wwan_pin_desc.md) | The WWAN_PIN_DESC structure represents the description or current status for a Personal Identification Number (PIN). |
| [_WWAN_PIN_INFO structure](ns-wwan-_wwan_pin_info.md) | The WWAN_PIN_INFO structure represents PIN type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device. |
| [_WWAN_PIN_LIST structure](ns-wwan-_wwan_pin_list.md) | The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs). |
| [_WWAN_PROVIDER structure](ns-wwan-_wwan_provider.md) | The WWAN_PROVIDER structure represents details about a network provider. |
| [_WWAN_PROVIDER2 structure](ns-wwan-_wwan_provider2.md) | The WWAN_PROVIDER2 structure describes the details of a network provider. |
| [_WWAN_RADIO_STATE structure](ns-wwan-_wwan_radio_state.md) | The WWAN_RADIO_STATE structure represents the hardware-based and software-based radio power states of the MB device. |
| [_WWAN_READY_INFO structure](ns-wwan-_wwan_ready_info.md) | The WWAN_READY_INFO structure represents the ready-state of the MB device. |
| [_WWAN_REGISTRATION_STATE structure](ns-wwan-_wwan_registration_state.md) | The WWAN_REGISTRATION_STATE structure represents the registration state of the MB device. |
| [_WWAN_SERVICE_ACTIVATION structure](ns-wwan-_wwan_service_activation.md) | The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with service activation. |
| [_WWAN_SERVICE_ACTIVATION_STATUS structure](ns-wwan-_wwan_service_activation_status.md) | The WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the MB device. |
| [_WWAN_SET_CONTEXT structure](ns-wwan-_wwan_set_context.md) | The WWAN_SET_CONTEXT structure represents a provisioned context with a network provider identification that is supported by the MB device. |
| [_WWAN_SET_CONTEXT_STATE structure](ns-wwan-_wwan_set_context_state.md) | The WWAN_SET_CONTEXT_STATE structure represents the command to set the Packet Data Protocol (PDP) context state of the MB device. |
| [_WWAN_SET_REGISTER_STATE structure](ns-wwan-_wwan_set_register_state.md) | The WWAN_SET_REGISTER_STATE structure represents the command to set the MB device's registration mode and the network provider it should register with. |
| [_WWAN_SET_SIGNAL_INDICATION structure](ns-wwan-_wwan_set_signal_indication.md) | The WWAN_SET_SIGNAL_INDICATION structure represents the frequency of RSSI interval and RSSI threshold notifications. |
| [_WWAN_SET_SMS_CONFIGURATION structure](ns-wwan-_wwan_set_sms_configuration.md) | The WWAN_SET_SMS_CONFIGURATION structure represents how MB devices support SMS configuration. |
| [_WWAN_SET_UICC_RESET structure](ns-wwan-_wwan_set_uicc_reset.md) | The WWAN_SET_UICC_RESET structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC smart card. |
| [_WWAN_SIGNAL_STATE structure](ns-wwan-_wwan_signal_state.md) | The WWAN_SIGNAL_STATE structure represents the signal state of the MB device. |
| [_WWAN_SLOT_INFO structure](ns-wwan-_wwan_slot_info.md) | The WWAN_SLOT_INFO structure represents the status of a specific SIM card slot on the modem. |
| [_WWAN_SMS_CDMA_RECORD structure](ns-wwan-_wwan_sms_cdma_record.md) | The WWAN_SMS_CDMA_RECORD structure represents CDMA-based SMS text message records. |
| [_WWAN_SMS_CONFIGURATION structure](ns-wwan-_wwan_sms_configuration.md) | The WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device. |
| [_WWAN_SMS_FILTER structure](ns-wwan-_wwan_sms_filter.md) | The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device. |
| [_WWAN_SMS_PDU_RECORD structure](ns-wwan-_wwan_sms_pdu_record.md) | The WWAN_SMS_PDU_RECORD structure represents a PDU-style SMS message record. |
| [_WWAN_SMS_READ structure](ns-wwan-_wwan_sms_read.md) | The WWAN_SMS_READ structure represents the format and filter of SMS messages to read. |
| [_WWAN_SMS_SEND structure](ns-wwan-_wwan_sms_send.md) | The WWAN_SMS_SEND structure represents an SMS text message to send. |
| [_WWAN_SMS_SEND_CDMA structure](ns-wwan-_wwan_sms_send_cdma.md) | The WWAN_SMS_SEND_CDMA structure represents a CDMA-based SMS text message to send. |
| [_WWAN_SMS_SEND_PDU structure](ns-wwan-_wwan_sms_send_pdu.md) | The WWAN_SMS_SEND_PDU structure represents a PDU-style SMS message. |
| [_WWAN_SMS_STATUS structure](ns-wwan-_wwan_sms_status.md) | The WWAN_SMS_STATUS structure represents the status of the SMS message store. |
| [_WWAN_SUPPORTED_DEVICE_SERVICES structure](ns-wwan-_wwan_supported_device_services.md) | The WWAN_SUPPORTED_DEVICE_SERVICES structure describes information about device services supported by the miniport driver. |
| [_WWAN_SYS_CAPS_INFO structure](ns-wwan-_wwan_sys_caps_info.md) | The WWAN_SYS_CAPS_INFO structure represents the modem's system capability. |
| [_WWAN_TDSCDMA_MRL structure](ns-wwan-_wwan_tdscdma_mrl.md) | The WWAN_TDSCDMA_MRL structure represents the measured results list (MRL) of neighboring TDSCDMA cells. |
| [_WWAN_TDSCDMA_MRL_INFO structure](ns-wwan-_wwan_tdscdma_mrl_info.md) | The WWAN_TDSCDMA_MRL_INFO structure represents information about a neighboring TDSCDMA cell. |
| [_WWAN_TDSCDMA_SERVING_CELL_INFO structure](ns-wwan-_wwan_tdscdma_serving_cell_info.md) | The WWAN_TDSCDMA_SERVING_CELL_INFO structure represents information about the TDSCDMA serving cell. |
| [_WWAN_UICC_RESET_INFO structure](ns-wwan-_wwan_uicc_reset_info.md) | The WWAN_UICC_RESET_INFO structure represents the passthrough status of a modem miniport adapter for a UICC smart card. |
| [_WWAN_UMTS_MRL structure](ns-wwan-_wwan_umts_mrl.md) | The WWAN_UMTS_MRL structure contains the measured results list (MRL) of neighboring UMTS cells. |
| [_WWAN_UMTS_MRL_INFO structure](ns-wwan-_wwan_umts_mrl_info.md) | The WWAN_UMTS_MRL_INFO structure represents information about a neighboring UMTS cell. |
| [_WWAN_UMTS_SERVING_CELL_INFO structure](ns-wwan-_wwan_umts_serving_cell_info.md) | The WWAN_UMTS_SERVING_CELL_INFO structure represents information about the UMTS serving cell. |
| [_WWAN_USSD_EVENT structure](ns-wwan-_wwan_ussd_event.md) | The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event. |
| [_WWAN_USSD_REQUEST structure](ns-wwan-_wwan_ussd_request.md) | The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) request. |
| [_WWAN_USSD_STRING structure](ns-wwan-_wwan_ussd_string.md) | The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string. |
| [_WWAN_VENDOR_SPECIFIC structure](ns-wwan-_wwan_vendor_specific.md) | The WWAN_VENDOR_SPECIFIC structure represents vendor-specific data. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WWAN_ACE_STATE enumeration](ne-wwan-_wwan_ace_state.md) | The WWAN_ACE_STATE enumeration lists the different kinds of auto-connect states. |
| [_WWAN_ACTIVATION_COMMAND enumeration](ne-wwan-_wwan_activation_command.md) | The WWAN_ACTIVATION_COMMAND enumeration lists the Packet Data Protocol (PDP) activation commands that are supported by the MB device. |
| [_WWAN_ACTIVATION_STATE enumeration](ne-wwan-_wwan_activation_state.md) | The WWAN_ACTIVATION_STATE enumeration lists the different Packet Data Protocol (PDP) context activation states that are supported by the MB device. |
| [_WWAN_ASYNC_GETSET_TYPE enumeration](ne-wwan-_wwan_async_getset_type.md) | The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests. |
| [_WWAN_AUTH_METHOD enumeration](ne-wwan-_wwan_auth_method.md) | The WWAN_AUTH_METHOD enumeration lists supported authentication methods. |
| [_WWAN_AUTH_PROTOCOL enumeration](ne-wwan-_wwan_auth_protocol.md) | The WWAN_AUTH_PROTOCOL enumeration lists the different types of authentication protocols that are supported by the MB device. |
| [_WWAN_CELLULAR_CLASS enumeration](ne-wwan-_wwan_cellular_class.md) | The WWAN_CELLULAR_CLASS enumeration lists the different classes of cellular technology that are supported by the MB device. |
| [_WWAN_COMPRESSION enumeration](ne-wwan-_wwan_compression.md) | The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB device. |
| [_WWAN_CONTEXT_TYPE enumeration](ne-wwan-_wwan_context_type.md) | The WWAN_CONTEXT_TYPE enumeration lists the different types of connection contexts that are supported by the MB device. |
| [_WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration](ne-wwan-_wwan_device_service_session_capability.md) | The WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration lists the different device service session operations that are supported by the device service. |
| [_WWAN_DEVICE_SERVICE_SESSION_STATE enumeration](ne-wwan-_wwan_device_service_session_state.md) | The WWAN_DEVICE_SERVICE_SESSION_STATE enumeration specifies the state of device service session. It can be used in a set operation to set the state of a session or can be used in an indication to report the state of a session. |
| [_WWAN_DEVICE_TYPE enumeration](ne-wwan-_wwan_device_type.md) | The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device. |
| [_WWAN_EMERGENCY_MODE enumeration](ne-wwan-_wwan_emergency_mode.md) | The WWAN_EMERGENCY_MODE enumeration lists the different types of emergency modes that are supported by the MB device. |
| [_WWAN_IP_TYPE enumeration](ne-wwan-_wwan_ip_type.md) | The WWAN_IP_TYPE enumeration lists the different levels of supported IP. |
| [_WWAN_MODEM_CONFIG_MODE enumeration](ne-wwan-_wwan_modem_config_mode.md) | The WWAN_MODEM_CONFIG_MODE enumeration lists modem configuration modes. |
| [_WWAN_MODEM_CONFIG_REASON enumeration](ne-wwan-_wwan_modem_config_reason.md) | The WWAN_MODEM_CONFIG_REASON enumeration lists definitions for reasons why a modem's configuration state change was triggered. |
| [_WWAN_MODEM_CONFIG_STATE enumeration](ne-wwan-_wwan_modem_config_state.md) | The WWAN_MODEM_CONFIG_STATE enumeration lists definitions used by the modem to inform the OS about its modem configuration state. |
| [_WWAN_MSG_STATUS enumeration](ne-wwan-_wwan_msg_status.md) | The WWAN_MSG_STATUS enumeration lists different SMS message statuses. |
| [_WWAN_PACKET_SERVICE_ACTION enumeration](ne-wwan-_wwan_packet_service_action.md) | The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions. |
| [_WWAN_PACKET_SERVICE_STATE enumeration](ne-wwan-_wwan_packet_service_state.md) | The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that are supported by the MB device. |
| [_WWAN_PCO_TYPE enumeration](ne-wwan-_wwan_pco_type.md) | The WWAN_PCO_TYPE enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host. |
| [_WWAN_PIN_FORMAT enumeration](ne-wwan-_wwan_pin_format.md) | The WWAN_PIN_FORMAT enumeration lists the different Personal Identification Number (PIN) formats that are supported by the MB device. |
| [_WWAN_PIN_MODE enumeration](ne-wwan-_wwan_pin_mode.md) | The WWAN_PIN_MODE enumeration lists the different states of a Personal Identification Number (PIN) type. |
| [_WWAN_PIN_OPERATION enumeration](ne-wwan-_wwan_pin_operation.md) | The WWAN_PIN_OPERATION enumeration lists the different Personal Identification Number (PIN) operations that are supported by the MB device. |
| [_WWAN_PIN_STATE enumeration](ne-wwan-_wwan_pin_state.md) | The WWAN_PIN_STATE enumeration describes whether the MB device or Subscriber Identity Module (SIM card) requires the user to enter a Personal Identification Number (PIN) to proceed to the next state. |
| [_WWAN_PIN_TYPE enumeration](ne-wwan-_wwan_pin_type.md) | The WWAN_PIN_TYPE enumeration lists the different types of Personal Identification Numbers (PINs) that are supported by the MB device. |
| [_WWAN_RADIO enumeration](ne-wwan-_wwan_radio.md) | The WWAN_RADIO enumeration lists the different types of radio power modes that are supported by the MB device. |
| [_WWAN_READY_STATE enumeration](ne-wwan-_wwan_ready_state.md) | The WWAN_READY_STATE enumeration lists the different device ready-states that are supported by the MB device. |
| [_WWAN_REGISTER_ACTION enumeration](ne-wwan-_wwan_register_action.md) | The WWAN_REGISTER_ACTION enumeration lists the different provider network registration actions that are supported by the MB device. |
| [_WWAN_REGISTER_MODE enumeration](ne-wwan-_wwan_register_mode.md) | The WWAN_REGISTER_MODE enumeration lists the different network selection modes which defines the way the device should select a network while registering. |
| [_WWAN_REGISTER_STATE enumeration](ne-wwan-_wwan_register_state.md) | The WWAN_REGISTER_STATE enumeration lists the different provider network registration states that are supported by the MB device. |
| [_WWAN_SIM_CLASS enumeration](ne-wwan-_wwan_sim_class.md) | The WWAN_SIM_CLASS enumeration lists the different types of Subscriber Identity Modules (SIMs) that are supported by the MB device. |
| [_WWAN_SMS_CDMA_ENCODING enumeration](ne-wwan-_wwan_sms_cdma_encoding.md) | The WWAN_SMS_CDMA_ENCODING enumeration lists the different SMS CDMA encoding formats that are supported by the MB device. |
| [_WWAN_SMS_CDMA_LANG enumeration](ne-wwan-_wwan_sms_cdma_lang.md) | The WWAN_SMS_CDMA_LANG enumeration lists the different SMS CDMA languages that are supported by the MB device. |
| [_WWAN_SMS_FLAG enumeration](ne-wwan-_wwan_sms_flag.md) | The WWAN_SMS_FLAG enumeration lists different flags to filter SMS text messages. |
| [_WWAN_SMS_FORMAT enumeration](ne-wwan-_wwan_sms_format.md) | The WWAN_SMS_FORMAT enumeration lists different Short Message Service (SMS) formats. |
| [_WWAN_STRUCT_TYPE enumeration](ne-wwan-_wwan_struct_type.md) | The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the WWAN_LIST_HEADER object in memory. |
| [_WWAN_UICCSLOT_STATE enumeration](ne-wwan-_wwan_uiccslot_state.md) | The WWAN_UICCSLOT_STATE enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state. |
| [_WWAN_UICC_PASSTHROUGH_ACTION enumeration](ne-wwan-_wwan_uicc_passthrough_action.md) | The WWAN_UICC_PASSTHROUGH_ACTION enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card. |
| [_WWAN_UICC_PASSTHROUGH_STATUS enumeration](ne-wwan-_wwan_uicc_passthrough_status.md) | The WWAN_UICC_PASSTHROUGH_STATUS enumeration defines the passthrough status of a modem miniport adapter for a UICC smart card. |
| [_WWAN_USSD_EVENT_TYPE enumeration](ne-wwan-_wwan_ussd_event_type.md) | The WWAN_USSD_EVENT_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) events. |
| [_WWAN_USSD_REQUEST_TYPE enumeration](ne-wwan-_wwan_ussd_request_type.md) | The WWAN_USSD_REQUEST_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) session requests. |
| [_WWAN_USSD_SESSION_STATE enumeration](ne-wwan-_wwan_ussd_session_state.md) | The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states. |
| [_WWAN_VOICE_CALL_STATE enumeration](ne-wwan-_wwan_voice_call_state.md) | The WWAN_VOICE_CALL_STATE enumeration lists the different voice call states that are supported by the MB device. |
| [_WWAN_VOICE_CLASS enumeration](ne-wwan-_wwan_voice_class.md) | The WWAN_VOICE_CLASS enumeration lists the different types of voice classes that are supported by the MB device. |
