---
UID: NA:wditypes
ms.assetid: 1d30a1e9-569c-3c34-a668-04e872d0716f
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wditypes.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Wditypes.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDI_CHANNEL_MAPPING_ENTRY structure](ns-wditypes-_wdi_channel_mapping_entry.md) | The WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry. |
| [_WDI_DATA_RATE_ENTRY structure](ns-wditypes-_wdi_data_rate_entry.md) | The WDI_DATA_RATE_ENTRY structure defines a data rate entry. |
| [_WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure](ns-wditypes-_wdi_ethertype_encapsulation_entry.md) | The WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure defines an EtherType encapsulation entry. |
| [_WDI_TYPE_MIC structure](ns-wditypes-_wdi_type_mic.md) | The WDI_TYPE_MIC structure defines the MIC (802.11r). |
| [_WDI_TYPE_NONCE structure](ns-wditypes-_wdi_type_nonce.md) | The WDI_TYPE_NONCE structure defines the SNonce or ANonce (802.11r). |
| [_WDI_TYPE_PMK_NAME structure](ns-wditypes-_wdi_type_pmk_name.md) | The WDI_TYPE_PMK_NAME structure defines the PMKR0Name or PMKR1Name (802.11r). |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDI_ACTION_FRAME_CATEGORY enumeration](ne-wditypes-_wdi_action_frame_category.md) | The WDI_ACTION_FRAME_CATEGORY enumeration defines the action frame categories. |
| [_WDI_ANQP_QUERY_STATUS enumeration](ne-wditypes-_wdi_anqp_query_status.md) | The WDI_ANQP_QUERY_STATUS enumeration defines the Access Network Query Protocol (ANQP) query status values. |
| [_WDI_ASSOC_STATUS enumeration](ne-wditypes-_wdi_assoc_status.md) | The WDI_ASSOC_STATUS enumeration defines the association status values. |
| [_WDI_AUTH_ALGORITHM enumeration](ne-wditypes-_wdi_auth_algorithm.md) | The WDI_AUTH_ALGORITHM enumeration defines the authentication algorithm values. |
| [_WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration](ne-wditypes-_wdi_bluetooth_coexistence_support.md) | The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration defines Bluetooth coexistence support values. |
| [_WDI_BSS_SELECTION_FLAGS enumeration](ne-wditypes-_wdi_bss_selection_flags.md) | The WDI_BSS_SELECTION_FLAGS enumeration defines flags for BSS selection. |
| [_WDI_CAN_SUSTAIN_AP_REASON enumeration](ne-wditypes-_wdi_can_sustain_ap_reason.md) | The WDI_CAN_SUSTAIN_AP_REASON enumeration defines the reasons the port is ready to receive a OID_WDI_TASK_START_AP request. |
| [_WDI_CIPHER_ALGORITHM enumeration](ne-wditypes-_wdi_cipher_algorithm.md) | The WDI_CIPHER_ALGORITHM enumeration defines the cipher algorithm values. |
| [_WDI_CIPHER_KEY_DIRECTION enumeration](ne-wditypes-_wdi_cipher_key_direction.md) | The WDI_CIPHER_KEY_DIRECTION enumeration defines the traffic directions decrypted by a cipher key. |
| [_WDI_CIPHER_KEY_TYPE enumeration](ne-wditypes-_wdi_cipher_key_type.md) | The WDI_CIPHER_KEY_TYPE enumeration defines the cipher key types. |
| [_WDI_CONNECTION_QUALITY_HINT enumeration](ne-wditypes-_wdi_connection_quality_hint.md) | The WDI_CONNECTION_QUALITY_HINT enumeration defines the Wi-Fi connection quality hints. |
| [_WDI_DATA_RATE_FLAGS enumeration](ne-wditypes-_wdi_data_rate_flags.md) | The WDI_DATA_RATE_FLAGS enumeration defines the data rate flags. |
| [_WDI_DS_INFO enumeration](ne-wditypes-_wdi_ds_info.md) | The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to. |
| [_WDI_ENCAPSULATION_TYPE enumeration](ne-wditypes-_wdi_encapsulation_type.md) | The WDI_ENCAPSULATION_TYPE enumeration defines the Wi-Fi encapsulation types. |
| [_WDI_EXEMPTION_PACKET_TYPE enumeration](ne-wditypes-_wdi_exemption_packet_type.md) | The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions. |
| [_WDI_FIPS_MODE enumeration](ne-wditypes-_wdi_fips_mode.md) | The WDI_FIPS_MODE enumeration defines values that specify if FIPS mode is enabled or not. |
| [_WDI_IHV_TASK_PRIORITY enumeration](ne-wditypes-_wdi_ihv_task_priority.md) | The WDI_IHV_TASK_PRIORITY enumeration defines IHV task priorities. |
| [_WDI_P2P_ACTION_FRAME_TYPE enumeration](ne-wditypes-_wdi_p2p_action_frame_type.md) | The WDI_P2P_ACTION_FRAME_TYPE enumeration defines the Wi-Fi Direct action frame types. |
| [_WDI_P2P_CHANNEL_INDICATE_REASON enumeration](ne-wditypes-_wdi_p2p_channel_indicate_reason.md) | The WDI_P2P_CHANNEL_INDICATE_REASON enumeration defines Wi-Fi Direct channel indication reason values. |
| [_WDI_P2P_DISCOVER_TYPE enumeration](ne-wditypes-_wdi_p2p_discover_type.md) | The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types. |
| [_WDI_P2P_GO_INTERNAL_RESET_POLICY enumeration](ne-wditypes-_wdi_p2p_go_internal_reset_policy.md) | The WDI_P2P_GO_INTERNAL_RESET_POLICY enumeration defines the Wi-Fi Direct Group Owner internal reset policies. |
| [_WDI_P2P_LISTEN_STATE enumeration](ne-wditypes-_wdi_p2p_listen_state.md) | The WDI_P2P_LISTEN_STATE enumeration defines the Wi-Fi Direct listen states. |
| [_WDI_P2P_SCAN_TYPE enumeration](ne-wditypes-_wdi_p2p_scan_type.md) | The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types. |
| [_WDI_P2P_SERVICE_DISCOVERY_TYPE enumeration](ne-wditypes-_wdi_p2p_service_discovery_type.md) | The WDI_P2P_SERVICE_DISCOVERY_TYPE enumeration defines the types of service discovery. |
| [_WDI_PACKET_FILTER_TYPE enumeration](ne-wditypes-_wdi_packet_filter_type.md) | The WDI_PACKET_FILTER_TYPE enumeration defines the packet filter types. |
| [_WDI_PHY_TYPE enumeration](ne-wditypes-_wdi_phy_type.md) | The WDI_PHY_TYPE enumeration defines the PHY types. |
| [_WDI_POWER_MODE_REASON_CODE enumeration](ne-wditypes-_wdi_power_mode_reason_code.md) | The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state. |
| [_WDI_POWER_SAVE_LEVEL enumeration](ne-wditypes-_wdi_power_save_level.md) | The WDI_POWER_SAVE_LEVEL enumeration defines the power save levels. |
| [_WDI_QOS_PROTOCOL enumeration](ne-wditypes-_wdi_qos_protocol.md) | The WDI_QOS_PROTOCOL enumeration defines Wi-Fi QOS protocols. |
| [_WDI_RADIO_MEASUREMENT_ACTION enumeration](ne-wditypes-_wdi_radio_measurement_action.md) | The WDI_RADIO_MEASUREMENT_ACTION enumeration defines the radio measurement actions. |
| [_WDI_ROAM_TRIGGER enumeration](ne-wditypes-_wdi_roam_trigger.md) | The WDI_ROAM_TRIGGER enumeration defines roam triggers. |
| [_WDI_SCAN_TRIGGER enumeration](ne-wditypes-_wdi_scan_trigger.md) | The WDI_SCAN_TRIGGER enumeration defines the scan trigger values. |
| [_WDI_SCAN_TYPE enumeration](ne-wditypes-_wdi_scan_type.md) | The WDI_SCAN_TYPE enumeration defines the scan types. |
| [_WDI_STOP_AP_REASON enumeration](ne-wditypes-_wdi_stop_ap_reason.md) | The WDI_STOP_AP_REASON enumeration defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs. |
| [_WDI_WNM_ACTION enumeration](ne-wditypes-_wdi_wnm_action.md) | The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames. |
| [_WDI_WPS_CONFIGURATION_METHOD enumeration](ne-wditypes-_wdi_wps_configuration_method.md) | The WDI_WPS_CONFIGURATION_METHOD enumeration defines WPS configuration methods. |
