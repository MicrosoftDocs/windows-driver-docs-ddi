---
UID: NA:nfccx
ms.assetid: e31e267f-9d28-39c5-9b01-ccb44c235455
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Nfccx.h header



This header is used by Near field communications (NFC). For more information, see
- [Near field communications (NFC)](../_nfpdrivers/index.md)

Nfccx.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NFC_CX_CLIENT_CONFIG_INIT function](nf-nfccx-nfc_cx_client_config_init.md) | The NFC_CX_CLIENT_CONFIG_INIT function initializes the NFC_CX_CLIENT_CONFIG structure. |
| [NFC_CX_LLCP_CONFIG_INIT function](nf-nfccx-nfc_cx_llcp_config_init.md) | The NFC_CX_LLCP_CONFIG_INIT function initializes the NFC_CX_LLCP_CONFIG structure. |
| [NFC_CX_RF_DISCOVERY_CONFIG_INIT function](nf-nfccx-nfc_cx_rf_discovery_config_init.md) | The NFC_CX_RF_DISCOVERY_CONFIG_INIT function initializes the NFC_CX_RF_DISCOVERY_CONFIG structure. |
| [NfcCxDeviceDeinitialize function](nf-nfccx-nfccxdevicedeinitialize.md) | Called by the client driver after a WDF device has been created during the AddDevice routine. |
| [NfcCxDeviceInitConfig function](nf-nfccx-nfccxdeviceinitconfig.md) | Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged |
| [NfcCxDeviceInitialize function](nf-nfccx-nfccxdeviceinitialize.md) | Called by the client driver after a WDF device has been created during the AddDevice routine. |
| [NfcCxHardwareEvent function](nf-nfccx-nfccxhardwareevent.md) | Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following |
| [NfcCxNciReadNotification function](nf-nfccx-nfccxncireadnotification.md) | Called by the client driver when a read packet is available. |
| [NfcCxRegisterSequenceHandler function](nf-nfccx-nfccxregistersequencehandler.md) | Called by the client driver during initialization to register for handling specific sequences. |
| [NfcCxSetLlcpConfig function](nf-nfccx-nfccxsetllcpconfig.md) | Called by the client driver to configure the LLCP parameters. |
| [NfcCxSetRfDiscoveryConfig function](nf-nfccx-nfccxsetrfdiscoveryconfig.md) | Called by the client driver to configure the RF discovery parameters. |
| [NfcCxUnregisterSequenceHandler function](nf-nfccx-nfccxunregistersequencehandler.md) | Called by the client driver during device shutdown to unregister for the previously registered sequence handler callback. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_NFC_CX_DEVICE_IO_CONTROL callback](nc-nfccx-evt_nfc_cx_device_io_control.md) | Called by the NFC CX to send an unhandled IOCTL to the client driver. |
| [EVT_NFC_CX_SEQUENCE_HANDLER callback](nc-nfccx-evt_nfc_cx_sequence_handler.md) | Called by the NFC CX to notify the client driver to handle the specific registered sequence. |
| [EVT_NFC_CX_WRITE_NCI_PACKET callback](nc-nfccx-evt_nfc_cx_write_nci_packet.md) | Called by the NFC CX to send a write packet to the client driver. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NFCCX_DRIVER_GLOBALS structure](ns-nfccx-_nfccx_driver_globals.md) | "." |
| [_NFC_CX_CLIENT_CONFIG structure](ns-nfccx-_nfc_cx_client_config.md) | The NFC_CX_CLIENT_CONFIG structure is an input parameter to NfcCxDeviceInitConfig. |
| [_NFC_CX_HARDWARE_EVENT structure](ns-nfccx-_nfc_cx_hardware_event.md) | The NFC_CX_HARDWARE_EVENT structure is an input parameter to NfcCxHardwareEvent. |
| [_NFC_CX_LLCP_CONFIG structure](ns-nfccx-_nfc_cx_llcp_config.md) | The NFC_CX_LLCP_CONFIG structure is an input parameter to NfcCxSetLlcpConfig. |
| [_NFC_CX_RF_DISCOVERY_CONFIG structure](ns-nfccx-_nfc_cx_rf_discovery_config.md) | The NFC_CX_RF_DISCOVERY_CONFIG structure contains RF discovery configuration settings. Discovery configuration should be completed during initialization after calling NfcDxDeviceInitialize, otherwise an error is returned. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NFC_CX_CE_MODE_CONFIG enumeration](ne-nfccx-_nfc_cx_ce_mode_config.md) | This enumeration specifies CE listening mode flags. |
| [_NFC_CX_DEVICE_MODE enumeration](ne-nfccx-_nfc_cx_device_mode.md) | Specifies device mode flags. |
| [_NFC_CX_DRIVER_FLAGS enumeration](ne-nfccx-_nfc_cx_driver_flags.md) | Specifies run-time driver flags. |
| [_NFC_CX_HOST_ACTION enumeration](ne-nfccx-_nfc_cx_host_action.md) | The NFC_CX_HOST_ACTION enumeration specifies host actions. |
| [_NFC_CX_NFCIP_MODE_CONFIG enumeration](ne-nfccx-_nfc_cx_nfcip_mode_config.md) | The NFC_CX_NFCIP_MODE_CONFIG enumeration specifies the NFC-IP initiator mode. |
| [_NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration](ne-nfccx-_nfc_cx_nfcip_tgt_mode_config.md) | The NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration specifies NFC-IP target mode. |
| [_NFC_CX_POLL_BAILOUT_CONFIG enumeration](ne-nfccx-_nfc_cx_poll_bailout_config.md) | The NFC_CX_POLL_BAILOUT_CONFIG enumeration specifies poll mode bail out. |
| [_NFC_CX_POLL_MODE_CONFIG enumeration](ne-nfccx-_nfc_cx_poll_mode_config.md) | The NFC_CX_POLL_MODE_CONFIG enumeration specifies poll mode. |
| [_NFC_CX_SEQUENCE enumeration](ne-nfccx-_nfc_cx_sequence.md) | The NFC_CX_SEQUENCE enumeration specifies sequences. |
| [_NFC_CX_TRANSPORT_TYPE enumeration](ne-nfccx-_nfc_cx_transport_type.md) | The NFC_CX_TRANSPORT_TYPE enumeration specifies transport types. |
