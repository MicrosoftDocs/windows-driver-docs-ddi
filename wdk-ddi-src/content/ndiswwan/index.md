---
UID: NA:ndiswwan
ms.assetid: 8bf083bd-9288-34f9-a2de-682644a9d03d
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ndiswwan.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Ndiswwan.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_NDIS_WWAN_AUTH_CHALLENGE structure](ns-ndiswwan-_ndis_wwan_auth_challenge.md) | The NDIS_WWAN_AUTH_CHALLENGE structure represents an authentication challenge used by one of the authentication methods. |
| [_NDIS_WWAN_AUTH_RESPONSE structure](ns-ndiswwan-_ndis_wwan_auth_response.md) | The NDIS_WWAN_AUTH_RESPONSE structure represents a response from one of the authentication methods. |
| [_NDIS_WWAN_BASE_STATIONS_INFO structure](ns-ndiswwan-_ndis_wwan_base_stations_info.md) | The NDIS_WWAN_BASE_STATIONS_INFO structure contains information about both serving and neighboring base stations. |
| [_NDIS_WWAN_BASE_STATIONS_INFO_REQ structure](ns-ndiswwan-_ndis_wwan_base_stations_info_req.md) | The NDIS_WWAN_BASE_STATIONS_INFO_REQ structure is used in OID_WWAN_BASE_STATIONS_INFO query requests to configure aspects of cellular base station information to be used in response. |
| [_NDIS_WWAN_CONTEXT_STATE structure](ns-ndiswwan-_ndis_wwan_context_state.md) | The NDIS_WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB device. |
| [_NDIS_WWAN_DEVICE_CAPS structure](ns-ndiswwan-_ndis_wwan_device_caps.md) | The NDIS_WWAN_DEVICE_CAPS structure represents the capabilities of the MB device. |
| [_NDIS_WWAN_DEVICE_CAPS_EX structure](ns-ndiswwan-_ndis_wwan_device_caps_ex.md) | The NDIS_WWAN_DEVICE_CAPS_EX structure represents the capabilities of the MB device. |
| [_NDIS_WWAN_DEVICE_RESET_STATUS structure](ns-ndiswwan-_ndis_wwan_device_reset_status.md) | The NDIS_WWAN_DEVICE_RESET_STATUS structure represents a modem device's reset status. It is sent to the MB host in the NDIS_STATUS_WWAN_DEVICE_RESET_STATUS notification in an asynchronous response to an OID_WWAN_DEVICE_RESET set request. |
| [_NDIS_WWAN_DEVICE_SERVICE_COMMAND structure](ns-ndiswwan-_ndis_wwan_device_service_command.md) | The NDIS_WWAN_DEVICE_SERVICE_COMMAND structure describes device service command data. |
| [_NDIS_WWAN_DEVICE_SERVICE_EVENT structure](ns-ndiswwan-_ndis_wwan_device_service_event.md) | The NDIS_WWAN_DEVICE_SERVICE_EVENT structure describes unsolicited device service data that were not initiated by commands from Windows. |
| [_NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure](ns-ndiswwan-_ndis_wwan_device_service_response.md) | The NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure represents device service data from the transaction completion of a device service command. |
| [_NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure](ns-ndiswwan-_ndis_wwan_device_service_session_info.md) | The NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO structure represents the status of a device service session. |
| [_NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure](ns-ndiswwan-_ndis_wwan_device_service_session_read.md) | The NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure represents device service session data that has been read by the miniport driver from the MB device. |
| [_NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure](ns-ndiswwan-_ndis_wwan_device_service_session_write.md) | The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents device service session data to be sent from the host to the MB device. |
| [_NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure](ns-ndiswwan-_ndis_wwan_device_service_session_write_complete.md) | The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure represents the status of a device service session write operation. |
| [_NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure](ns-ndiswwan-_ndis_wwan_device_service_subscription.md) | The NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structures encapsulates the data for NDIS_STATUS_WWAN_ DEVICE_SERVICE_SUBSCRIPTION. |
| [_NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure](ns-ndiswwan-_ndis_wwan_device_service_supported_commands.md) | The NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service. |
| [_NDIS_WWAN_DEVICE_SET_SERVICE_SESSION structure](ns-ndiswwan-_ndis_wwan_device_set_service_session.md) | The NDIS_WWAN_SET_DEVICE_SERVICE_SESSION structure represents a session state operation to be performed on a device service. |
| [_NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure](ns-ndiswwan-_ndis_wwan_device_slot_mapping_info.md) | The NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship of the MB device. |
| [_NDIS_WWAN_DRIVER_CAPS structure](ns-ndiswwan-_ndis_wwan_driver_caps.md) | The NDIS_WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver. |
| [_NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure](ns-ndiswwan-_ndis_wwan_enumerate_device_service_commands.md) | The NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure represents the commands supported by a device service. |
| [_NDIS_WWAN_GET_SLOT_INFO structure](ns-ndiswwan-_ndis_wwan_get_slot_info.md) | The NDIS_WWAN_GET_SLOT_INFO structure represents the status of a slot in the modem of the MB device. |
| [_NDIS_WWAN_GET_VISIBLE_PROVIDERS structure](ns-ndiswwan-_ndis_wwan_get_visible_providers.md) | The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers. |
| [_NDIS_WWAN_HOME_PROVIDER structure](ns-ndiswwan-_ndis_wwan_home_provider.md) | The NDIS_WWAN_HOME_PROVIDER structure represents details about the home network provider. |
| [_NDIS_WWAN_HOME_PROVIDER2 structure](ns-ndiswwan-_ndis_wwan_home_provider2.md) | The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider. |
| [_NDIS_WWAN_IP_ADDRESS_STATE structure](ns-ndiswwan-_ndis_wwan_ip_address_state.md) | The NDIS_WWAN_IP_ADDRESS_STATE structure represents the IP address of a PDP context. |
| [_NDIS_WWAN_MAC_INFO structure](ns-ndiswwan-_ndis_wwan_mac_info.md) | The NDIS_WWAN_MAC_INFO structure represents NDIS port information for a PDP context. |
| [_NDIS_WWAN_MAC_PARAMETERS structure](ns-ndiswwan-_ndis_wwan_mac_parameters.md) | The NDIS_WWAN_MAC_PARAMETERS structure is used by OID_WWAN_CREATE_MAC when processing a request to create an NDIS port for a new PDP context. |
| [_NDIS_WWAN_MODEM_CONFIG_INFO structure](ns-ndiswwan-_ndis_wwan_modem_config_info.md) | The NDIS_WWAN_MODEM_CONFIG_INFO structure represents the modem's configuration information. |
| [_NDIS_WWAN_NETWORK_IDLE_HINT structure](ns-ndiswwan-_ndis_wwan_network_idle_hint.md) | The NDIS_WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface. |
| [_NDIS_WWAN_PACKET_SERVICE_STATE structure](ns-ndiswwan-_ndis_wwan_packet_service_state.md) | The NDIS_WWAN_PACKET_SERVICE_STATE structure represents the packet service attachment state of the MB device. |
| [_NDIS_WWAN_PCO_STATUS structure](ns-ndiswwan-_ndis_wwan_pco_status.md) | The NDIS_WWAN_PCO_STATUS structure represents the Protocol Configuration Option (PCO) status of the modem. |
| [_NDIS_WWAN_PIN_INFO structure](ns-ndiswwan-_ndis_wwan_pin_info.md) | The NDIS_WWAN_PIN_INFO structure represents the type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device. |
| [_NDIS_WWAN_PIN_LIST structure](ns-ndiswwan-_ndis_wwan_pin_list.md) | The NDIS_WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs). |
| [_NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure](ns-ndiswwan-_ndis_wwan_preferred_multicarrier_providers.md) | The NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multi-carrier providers and the number of providers in the list. |
| [_NDIS_WWAN_PREFERRED_PROVIDERS structure](ns-ndiswwan-_ndis_wwan_preferred_providers.md) | The NDIS_WWAN_PREFERRED_PROVIDERS structure represents a list of preferred providers including the number of providers in the list. |
| [_NDIS_WWAN_PRESHUTDOWN_STATE structure](ns-ndiswwan-_ndis_wwan_preshutdown_state.md) | The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status. |
| [_NDIS_WWAN_PROVISIONED_CONTEXTS structure](ns-ndiswwan-_ndis_wwan_provisioned_contexts.md) | The NDIS_WWAN_PROVISIONED_CONTEXTS structure represents a list of provisioned contexts and the number of provisioned contexts in the list. |
| [_NDIS_WWAN_RADIO_STATE structure](ns-ndiswwan-_ndis_wwan_radio_state.md) | The NDIS_WWAN_RADIO_STATE structure represents the hardware-based and software-based radio power states of the MB device. |
| [_NDIS_WWAN_READY_INFO structure](ns-ndiswwan-_ndis_wwan_ready_info.md) | The NDIS_WWAN_READY_INFO structure represents the ready-state of the MB device and Subscriber Identity Module (SIM card). |
| [_NDIS_WWAN_REGISTRATION_STATE structure](ns-ndiswwan-_ndis_wwan_registration_state.md) | The NDIS_WWAN_REGISTRATION_STATE structure represents the registration state of the MB device. |
| [_NDIS_WWAN_SERVICE_ACTIVATION structure](ns-ndiswwan-_ndis_wwan_service_activation.md) | The NDIS_WWAN_SERVICE_ACTIVATION structure represents the command that is used to set the service activation state of the MB device in order to obtain access to the provider's network. |
| [_NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure](ns-ndiswwan-_ndis_wwan_service_activation_status.md) | The NDIS_WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the MB device. |
| [_NDIS_WWAN_SET_CONTEXT_STATE structure](ns-ndiswwan-_ndis_wwan_set_context_state.md) | The NDIS_WWAN_SET_CONTEXT_STATE structure represents the command to set the context state of the MB device. |
| [_NDIS_WWAN_SET_DEVICE_RESET structure](ns-ndiswwan-_ndis_wwan_set_device_reset.md) | The NDIS_WWAN_SET_DEVICE_RESET structure represents a command to reset a modem device. It is sent as part of an OID_WWAN_DEVICE_RESET set request. |
| [_NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO structure](ns-ndiswwan-_ndis_wwan_set_device_slot_mapping_info.md) | The NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO structure sets the executor-to-slot mapping relationship of the MB device. |
| [_NDIS_WWAN_SET_HOME_PROVIDER structure](ns-ndiswwan-_ndis_wwan_set_home_provider.md) | The NDIS_WWAN_SET_HOME_PROVIDER structure describes a home provider. |
| [_NDIS_WWAN_SET_PACKET_SERVICE structure](ns-ndiswwan-_ndis_wwan_set_packet_service.md) | The NDIS_WWAN_SET_PACKET_SERVICE structure represents the packet service state of the MB device. |
| [_NDIS_WWAN_SET_PIN structure](ns-ndiswwan-_ndis_wwan_set_pin.md) | The NDIS_WWAN_SET_PIN structure represents what PIN action to take on the MB device. |
| [_NDIS_WWAN_SET_PIN_EX structure](ns-ndiswwan-_ndis_wwan_set_pin_ex.md) | The NDIS_WWAN_SET_PIN_EX structure represents what PIN action to take on the MB device. |
| [_NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure](ns-ndiswwan-_ndis_wwan_set_preferred_multicarrier_providers.md) | The NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multicarrier providers associated with the MB device. |
| [_NDIS_WWAN_SET_PREFERRED_PROVIDERS structure](ns-ndiswwan-_ndis_wwan_set_preferred_providers.md) | The NDIS_WWAN_SET_PREFERRED_PROVIDERS structure represents the list of preferred providers associated with the MB device. |
| [_NDIS_WWAN_SET_PRESHUTDOWN_STATE structure](ns-ndiswwan-_ndis_wwan_set_preshutdown_state.md) | The NDIS_WWAN_SET_PRESHUTDOWN_STATE structure represents the command to notify the modem to finish all operations and prepare to shut down. |
| [_NDIS_WWAN_SET_PROVISIONED_CONTEXT structure](ns-ndiswwan-_ndis_wwan_set_provisioned_context.md) | The NDIS_WWAN_SET_PROVISIONED_CONTEXT structure represents the command to set the provisioned context state of the MB device. |
| [_NDIS_WWAN_SET_RADIO_STATE structure](ns-ndiswwan-_ndis_wwan_set_radio_state.md) | The NDIS_WWAN_SET_RADIO_STATE structure represents the power action to take on the MB device's radio. |
| [_NDIS_WWAN_SET_REGISTER_STATE structure](ns-ndiswwan-_ndis_wwan_set_register_state.md) | The NDIS_WWAN_SET_REGISTER_STATE structure represents the network provider registration state of the MB device. |
| [_NDIS_WWAN_SET_SIGNAL_INDICATION structure](ns-ndiswwan-_ndis_wwan_set_signal_indication.md) | The NDIS_WWAN_SET_SIGNAL_INDICATION structure represents the signal indication of the MB device. |
| [_NDIS_WWAN_SET_SMS_CONFIGURATION structure](ns-ndiswwan-_ndis_wwan_set_sms_configuration.md) | The NDIS_WWAN_SET_SMS_CONFIGURATION structure represents the SMS configuration of the MB device. |
| [_NDIS_WWAN_SET_UICC_RESET structure](ns-ndiswwan-_ndis_wwan_set_uicc_reset.md) | The NDIS_WWAN_SET_UICC_RESET structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC card. |
| [_NDIS_WWAN_SIGNAL_STATE structure](ns-ndiswwan-_ndis_wwan_signal_state.md) | The NDIS_WWAN_SIGNAL_STATE structure represents the signal state of the MB device. |
| [_NDIS_WWAN_SLOT_INFO structure](ns-ndiswwan-_ndis_wwan_slot_info.md) | The NDIS_WWAN_SLOT_INFO structure represents the information about a slot in the modem of the MB device. |
| [_NDIS_WWAN_SMS_CONFIGURATION structure](ns-ndiswwan-_ndis_wwan_sms_configuration.md) | The NDIS_WWAN_SMS_CONFIGURATION structure represents the SMS configuration of the MB device. |
| [_NDIS_WWAN_SMS_DELETE structure](ns-ndiswwan-_ndis_wwan_sms_delete.md) | The NDIS_WWAN_SMS_DELETE structure represents an SMS message to delete. |
| [_NDIS_WWAN_SMS_DELETE_STATUS structure](ns-ndiswwan-_ndis_wwan_sms_delete_status.md) | The NDIS_WWAN_SMS_DELETE_STATUS structure represents the status of a deleted SMS text message. |
| [_NDIS_WWAN_SMS_READ structure](ns-ndiswwan-_ndis_wwan_sms_read.md) | The NDIS_WWAN_SMS_READ structure represents an SMS message to read. |
| [_NDIS_WWAN_SMS_RECEIVE structure](ns-ndiswwan-_ndis_wwan_sms_receive.md) | The NDIS_WWAN_SMS_RECEIVE structure represents a list of received SMS messages and the number of messages in the list. |
| [_NDIS_WWAN_SMS_SEND structure](ns-ndiswwan-_ndis_wwan_sms_send.md) | The NDIS_WWAN_SMS_SEND structure represents an SMS message to send. |
| [_NDIS_WWAN_SMS_SEND_STATUS structure](ns-ndiswwan-_ndis_wwan_sms_send_status.md) | The NDIS_WWAN_SMS_SEND_STATUS structure represents the status of a sent SMS text message. |
| [_NDIS_WWAN_SMS_STATUS structure](ns-ndiswwan-_ndis_wwan_sms_status.md) | The NDIS_WWAN_SMS_STATUS structure represents the status of the SMS message store. |
| [_NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure](ns-ndiswwan-_ndis_wwan_subscribe_device_service_events.md) | The NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure encapsulates data for OID_WWAN_SUBSCRIBE_DEVICE_SERVICES_EVENTS. |
| [_NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure](ns-ndiswwan-_ndis_wwan_supported_device_services.md) | The NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure describes a list of supported device services. |
| [_NDIS_WWAN_SYS_CAPS_INFO structure](ns-ndiswwan-_ndis_wwan_sys_caps_info.md) | The NDIS_WWAN_SYS_CAPS_INFO structure represents the overall modem's system capability. |
| [_NDIS_WWAN_UICC_RESET_INFO structure](ns-ndiswwan-_ndis_wwan_uicc_reset_info.md) | The NDIS_WWAN_UICC_RESET_INFO structure represents the passthrough status of a modem miniport adapter for a UICC smart card. |
| [_NDIS_WWAN_USSD_EVENT structure](ns-ndiswwan-_ndis_wwan_ussd_event.md) | The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS event. |
| [_NDIS_WWAN_USSD_REQUEST structure](ns-ndiswwan-_ndis_wwan_ussd_request.md) | The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS request. |
| [_NDIS_WWAN_VENDOR_SPECIFIC structure](ns-ndiswwan-_ndis_wwan_vendor_specific.md) | The NDIS_WWAN_VENDOR_SPECIFIC structure represents vendor-specific data. |
| [_NDIS_WWAN_VISIBLE_PROVIDERS structure](ns-ndiswwan-_ndis_wwan_visible_providers.md) | The NDIS_WWAN_VISIBLE_PROVIDERS structure represents a list of visible providers and the number of providers in the list. |
