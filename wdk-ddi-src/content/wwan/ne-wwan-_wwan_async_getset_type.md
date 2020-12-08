---
UID: NE:wwan._WWAN_ASYNC_GETSET_TYPE
title: _WWAN_ASYNC_GETSET_TYPE (wwan.h)
description: The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.
old-location: netvista\wwan_async_getset_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_ASYNC_GETSET_TYPE enumeration"]
ms.keywords: "*PWWAN_ASYNC_GETSET_TYPE, WWAN_ASYNC_GETSET_TYPE, WWAN_ASYNC_GETSET_TYPE enumeration [Network Drivers Starting with Windows Vista], WWAN_ASYNC_GETSET_TYPE_MAX, WwanAsyncAuthChallenge, WwanAsyncGetConnect, WwanAsyncGetDeviceCaps, WwanAsyncGetDeviceServiceCommand get request., WwanAsyncGetDeviceServices, WwanAsyncGetHomeProvider, WwanAsyncGetPacketService, WwanAsyncGetPin, WwanAsyncGetPinEx get request., WwanAsyncGetPinList, WwanAsyncGetPreferredProviders, WwanAsyncGetProvisionedContexts, WwanAsyncGetRadioState, WwanAsyncGetReadyInfo, WwanAsyncGetRegisterState, WwanAsyncGetSignalState, WwanAsyncGetSmsConfiguration, WwanAsyncGetVisibleProviders, WwanAsyncSetConnect, WwanAsyncSetDeviceServiceCommand, WwanAsyncSetHomeProvider, WwanAsyncSetPacketService, WwanAsyncSetPin, WwanAsyncSetPinEx, WwanAsyncSetPreferredProviders, WwanAsyncSetProfileIndex, WwanAsyncSetProvisionedContext, WwanAsyncSetRadioState, WwanAsyncSetRegisterState, WwanAsyncSetServiceActivation, WwanAsyncSetSignalState, WwanAsyncSetSmsConfiguration, WwanAsyncSetVendorSpecific, WwanAsyncSmsDelete, WwanAsyncSmsRead, WwanAsyncSmsSend, WwanAsyncSmsStatus, WwanAsyncSubscribeDeviceServiceEvents, WwanAsyncUssdRequest, _WWAN_ASYNC_GETSET_TYPE, netvista.wwan_async_getset_type, wwan/WWAN_ASYNC_GETSET_TYPE, wwan/WWAN_ASYNC_GETSET_TYPE_MAX, wwan/WwanAsyncAuthChallenge, wwan/WwanAsyncGetConnect, wwan/WwanAsyncGetDeviceCaps, wwan/WwanAsyncGetDeviceServiceCommand get request., wwan/WwanAsyncGetDeviceServices, wwan/WwanAsyncGetHomeProvider, wwan/WwanAsyncGetPacketService, wwan/WwanAsyncGetPin, wwan/WwanAsyncGetPinEx get request., wwan/WwanAsyncGetPinList, wwan/WwanAsyncGetPreferredProviders, wwan/WwanAsyncGetProvisionedContexts, wwan/WwanAsyncGetRadioState, wwan/WwanAsyncGetReadyInfo, wwan/WwanAsyncGetRegisterState, wwan/WwanAsyncGetSignalState, wwan/WwanAsyncGetSmsConfiguration, wwan/WwanAsyncGetVisibleProviders, wwan/WwanAsyncSetConnect, wwan/WwanAsyncSetDeviceServiceCommand, wwan/WwanAsyncSetHomeProvider, wwan/WwanAsyncSetPacketService, wwan/WwanAsyncSetPin, wwan/WwanAsyncSetPinEx, wwan/WwanAsyncSetPreferredProviders, wwan/WwanAsyncSetProfileIndex, wwan/WwanAsyncSetProvisionedContext, wwan/WwanAsyncSetRadioState, wwan/WwanAsyncSetRegisterState, wwan/WwanAsyncSetServiceActivation, wwan/WwanAsyncSetSignalState, wwan/WwanAsyncSetSmsConfiguration, wwan/WwanAsyncSetVendorSpecific, wwan/WwanAsyncSmsDelete, wwan/WwanAsyncSmsRead, wwan/WwanAsyncSmsSend, wwan/WwanAsyncSmsStatus, wwan/WwanAsyncSubscribeDeviceServiceEvents, wwan/WwanAsyncUssdRequest"
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WWAN_ASYNC_GETSET_TYPE, *PWWAN_ASYNC_GETSET_TYPE
f1_keywords:
 - _WWAN_ASYNC_GETSET_TYPE
 - wwan/_WWAN_ASYNC_GETSET_TYPE
 - PWWAN_ASYNC_GETSET_TYPE
 - wwan/PWWAN_ASYNC_GETSET_TYPE
 - WWAN_ASYNC_GETSET_TYPE
 - wwan/WWAN_ASYNC_GETSET_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_ASYNC_GETSET_TYPE
---

# _WWAN_ASYNC_GETSET_TYPE enumeration


## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.

## -enum-fields

### -field WwanAsyncGetDeviceCaps

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-device-caps">OID_WWAN_DEVICE_CAPS</a> get request.

### -field WwanAsyncGetReadyInfo

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-ready-info">OID_WWAN_READY_INFO</a> get request.

### -field WwanAsyncGetRadioState

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-radio-state">OID_WWAN_RADIO_STATE</a> get request.

### -field WwanAsyncSetRadioState

Asynchronous [OID_WWAN_RADIO_STATE](/windows-hardware/drivers/network/oid-wwan-radio-state) set request.

### -field WwanAsyncGetPin

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-pin">OID_WWAN_PIN</a> get request.

### -field WwanAsyncSetPin

Asynchronous [OID_WWAN_PIN](/windows-hardware/drivers/network/oid-wwan-pin) set request.

### -field WwanAsyncGetPinList

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-pin-list">OID_WWAN_PIN_LIST</a> get request.

### -field WwanAsyncGetHomeProvider

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-home-provider">OID_WWAN_HOME_PROVIDER</a> get request.

### -field WwanAsyncSetHomeProvider

Asynchronous [OID_WWAN_HOME_PROVIDER](/windows-hardware/drivers/network/oid-wwan-home-provider) set request.

### -field WwanAsyncGetPreferredProviders

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-preferred-providers">OID_WWAN_PREFERRED_PROVIDERS</a> get request.

### -field WwanAsyncSetPreferredProviders

Asynchronous [OID_WWAN_PREFERRED_PROVIDERS](/windows-hardware/drivers/network/oid-wwan-preferred-providers) set request.

### -field WwanAsyncGetVisibleProviders

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-visible-providers">OID_WWAN_VISIBLE_PROVIDERS</a> get request.

### -field WwanAsyncGetRegisterState

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-register-state">OID_WWAN_REGISTER_STATE</a> get request.

### -field WwanAsyncSetRegisterState

Asynchronous [OID_WWAN_REGISTER_STATE](/windows-hardware/drivers/network/oid-wwan-register-state) set request.

### -field WwanAsyncGetPacketService

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-packet-service">OID_WWAN_PACKET_SERVICE</a> get request.

### -field WwanAsyncSetPacketService

Asynchronous [OID_WWAN_PACKET_SERVICE](/windows-hardware/drivers/network/oid-wwan-packet-service) set request.

### -field WwanAsyncGetSignalState

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-signal-state">OID_WWAN_SIGNAL_STATE</a> get request.

### -field WwanAsyncSetSignalState

Asynchronous [OID_WWAN_SIGNAL_STATE](/windows-hardware/drivers/network/oid-wwan-signal-state) set request.

### -field WwanAsyncGetConnect

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-connect">OID_WWAN_CONNECT</a> get request.

### -field WwanAsyncSetConnect

Asynchronous [OID_WWAN_CONNECT](/windows-hardware/drivers/network/oid-wwan-connect) set request.

### -field WwanAsyncGetProvisionedContexts

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">OID_WWAN_PROVISIONED_CONTEXTS</a> get request.

### -field WwanAsyncSetProvisionedContext

Asynchronous [OID_WWAN_PROVISIONED_CONTEXTS](/windows-hardware/drivers/network/oid-wwan-provisioned-contexts) set request.

### -field WwanAsyncSetServiceActivation

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-service-activation">OID_WWAN_SERVICE_ACTIVATION</a> set request.

### -field WwanAsyncGetSmsConfiguration

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-sms-configuration">OID_WWAN_SMS_CONFIGURATION</a> get request.

### -field WwanAsyncSetSmsConfiguration

Asynchronous [OID_WWAN_SMS_CONFIGURATION](/windows-hardware/drivers/network/oid-wwan-sms-configuration) set request.

### -field WwanAsyncSmsRead

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-sms-read">OID_WWAN_SMS_READ</a> get request.

### -field WwanAsyncSmsSend

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-sms-send">OID_WWAN_SMS_SEND</a> set request.

### -field WwanAsyncSmsDelete

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-sms-delete">OID_WWAN_SMS_DELETE</a> set request.

### -field WwanAsyncSmsStatus

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-sms-status">OID_WWAN_SMS_STATUS</a> query request.

### -field WwanAsyncSetVendorSpecific

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-vendor-specific">OID_WWAN_VENDOR_SPECIFIC</a> set request.

### -field WwanAsyncSetProfileIndex

Reserved.

### -field WwanAsyncGetDeviceServices

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-device-services">OID_WWAN_DEVICE_SERVICES</a> get request.

### -field WwanAsyncSubscribeDeviceServiceEvents

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-subscribe-device-service-events">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a> set request.

### -field WwanAsyncAuthChallenge

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-auth-challenge">OID_WWAN_AUTH_CHALLENGE</a> query request.

### -field WwanAsyncUssdRequest

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-ussd">OID_WWAN_USSD</a> set request.

### -field WwanAsyncSetPinEx

Asynchronous <a href="/windows-hardware/drivers/network/oid-wwan-pin-ex">OID_WWAN_PIN_EX</a> set request.

### -field WwanAsyncGetPinEx

Asynchronous [OID_WWAN_PIN_EX](/windows-hardware/drivers/network/oid-wwan-pin-ex) get request.

### -field WwanAsyncGetDeviceServiceCommand

Asynchronous [OID_WWAN_DEVICE_SERVICE_COMMAND](/windows-hardware/drivers/network/oid-wwan-device-service-command) get request.

### -field WwanAsyncSetDeviceServiceCommand

Asynchronous [OID_WWAN_DEVICE_SERVICE_COMMAND](/windows-hardware/drivers/network/oid-wwan-device-service-command) set request.

### -field WwanAsyncQueryDeviceServiceSupportedCommands

Asynchronous [OID_WWAN_DEVICE_SERVICES](/windows-hardware/drivers/network/oid-wwan-device-services)

### -field WwanAsyncGetPreferredMultiCarrierProviders

Asynchronous [OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS](/windows-hardware/drivers/network/oid-wwan-preferred-multicarrier-providers) get request.

### -field WwanAsyncSetPreferredMultiCarrierProviders

Asynchronous [OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS](/windows-hardware/drivers/network/oid-wwan-preferred-multicarrier-providers) set request.

### -field WwanAsyncSetDeviceServiceSession

Asynchronous [OID_WWAN_DEVICE_SERVICE_SESSION](/windows-hardware/drivers/network/oid-wwan-device-service-session) set request.

### -field WwanAsyncWriteDeviceServiceSession

Asynchronous [OID_WWAN_DEVICE_SERVICE_SESSION_WRITE](/windows-hardware/drivers/network/oid-wwan-device-service-session-write) set request.

### -field WwanAsyncSetNetworkIdleHint

Asynchronous [OID_WWAN_NETWORK_IDLE_HINT](/windows-hardware/drivers/network/oid-wwan-network-idle-hint) set request.

### -field WwanAsyncSetPreshutdown

Asynchronous [OID_WWAN_PRESHUTDOWN](/windows-hardware/drivers/network/oid-wwan-preshutdown) set request.

### -field WwanAsyncGetAtr

Asynchronous OID_WWAN_UICC_ATR get request.

### -field WwanAsyncUiccOpenChannel

Asynchronous OID_WWAN_UICC_OPEN_CHANNEL set request.

### -field WwanAsyncUiccCloseChannel

Asynchronous OID_WWAN_UICC_CLOSE_CHANNEL set request.

### -field WwanAsyncUiccSendApdu

Asynchronous OID_WWAN_UICC_APDU set request.

### -field WwanAsyncUiccGetTerminalCapability

Asynchronous OID_WWAN_UICC_TERMINAL_CAPABILITY get request.

### -field WwanAsyncUiccSetTerminalCapability

Asynchronous OID_WWAN_UICC_TERMINAL_CAPABILITY set request.

### -field WwanAsyncGetPsMediaConfig

Asynchronous OID_WWAN_PS_MEDIA_CONFIG get request.

### -field WwanAsyncSetPsMediaConfig

Asynchronous OID_WWAN_PS_MEDIA_CONFIG set request.

### -field WwanAsyncGetSarConfig

Asynchronous [OID_WWAN_SAR_CONFIG](/windows-hardware/drivers/network/oid-wwan-sar-config) get request.

### -field WwanAsyncSetSarConfig

Asynchronous [OID_WWAN_SAR_CONFIG](/windows-hardware/drivers/network/oid-wwan-sar-config) set request.

### -field WwanAsyncGetSarTransmissionStatus

Asynchronous [OID_WWAN_SAR_TRANSMISSION_STATUS](/windows-hardware/drivers/network/oid-wwan-sar-transmission-status) get request.

### -field WwanAsyncSetSarTransmissionStatus

Asynchronous [OID_WWAN_SAR_TRANSMISSION_STATUS](/windows-hardware/drivers/network/oid-wwan-sar-transmission-status) set request.

### -field WwanAsyncGetNetworkBlacklist

Asynchronous [OID_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/oid-wwan-network-blacklist) get request.

### -field WwanAsyncSetNetworkBlacklist

Asynchronous [OID_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/oid-wwan-network-blacklist) set request.

### -field WwanAsyncGetLteAttachConfig

Asynchronous [OID_WWAN_LTE_ATTACH_CONFIG](/windows-hardware/drivers/network/oid-wwan-lte-attach-config) get request.

### -field WwanAsyncSetLteAttachConfig

Asynchronous [OID_WWAN_LTE_ATTACH_CONFIG](/windows-hardware/drivers/network/oid-wwan-lte-attach-config) set request.

### -field WwanAsyncGetLteAttachStatus

Asynchronous [OID_WWAN_LTE_ATTACH_STATUS](/windows-hardware/drivers/network/oid-wwan-lte-attach-status) get request.

### -field WwanAsyncSetLteAttachStatus

Asynchronous [OID_WWAN_LTE_ATTACH_STATUS](/windows-hardware/drivers/network/oid-wwan-lte-attach-status) set request.

### -field WwanAsyncGetSysCap

Asynchronous [OID_WWAN_SYS_CAPS_INFO](/windows-hardware/drivers/network/oid-wwan-sys-caps) get request.

### -field WwanAsyncGetDeviceCapsEx

Asynchronous [OID_WWAN_DEVICE_CAPS_EX](/windows-hardware/drivers/network/oid-wwan-device-caps-ex) get request.

### -field WwanAsyncGetUiccSlotMapping

Asynchronous [OID_WWAN_DEVICE_SLOT_MAPPING_INFO](/windows-hardware/drivers/network/oid-wwan-device-slot-mappings) get request.

### -field WwanAsyncSetUiccSlotMapping

Asynchronous [OID_WWAN_DEVICE_SLOT_MAPPING_INFO](/windows-hardware/drivers/network/oid-wwan-device-slot-mappings) set request.

### -field WwanAsyncGetUiccSlotInfo

Asynchronous [OID_WWAN_SLOT_INFO](/windows-hardware/drivers/network/oid-wwan-slot-info-status) get request.

### -field WwanAsyncGetModemConfigInfo

Asynchronous [OID_WWAN_MODEM_CONFIG_INFO](/windows-hardware/drivers/network/oid-wwan-modem-config-info) get request.

### -field WwanAsyncGetPcoStatus

Asynchronous [OID_WWAN_PCO](/windows-hardware/drivers/network/oid-wwan-pco) get request.

### -field WwanAsyncUiccGetReset

Asynchronous [OID_WWAN_UICC_RESET](/windows-hardware/drivers/network/oid-wwan-uicc-reset) get request.

### -field WwanAsyncUiccSetReset

Asynchronous [OID_WWAN_UICC_RESET](/windows-hardware/drivers/network/oid-wwan-uicc-reset) set request.

### -field WwanAsyncSetDeviceReset

Asynchronous [OID_WWAN_DEVICE_RESET](/windows-hardware/drivers/network/oid-wwan-device-reset) set request.

### -field WwanAsyncGetCellInfo

Asynchronous [OID_WWAN_BASE_STATIONS_INFO](/windows-hardware/drivers/network/oid-wwan-base-stations-info) get request.

### -field WwanAsyncGetMPDP

Asynchronous [OID_WWAN_MPDP](/windows-hardware/drivers/network/oid-wwan-mpdp) get request.

### -field WwanAsyncSetMPDP

Asynchronous [OID_WWAN_MPDP](/windows-hardware/drivers/network/oid-wwan-mpdp) set request.

### -field WWAN_ASYNC_GETSET_TYPE_MAX

The maximum number of entries in the **WWAN_ASYNC_GETSET_TYPE** enumeration.

## -see-also

<a href="/windows-hardware/drivers/network/mb-data-model">MB Data Model</a>
