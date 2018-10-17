---
UID: NE:wwan._WWAN_ASYNC_GETSET_TYPE
title: "_WWAN_ASYNC_GETSET_TYPE"
author: windows-driver-content
description: The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.
old-location: netvista\wwan_async_getset_type.htm
tech.root: netvista
ms.assetid: 2FECDA17-7B38-4636-AFAF-D923AECFAF68
ms.date: 5/2/2018
ms.keywords: "*PWWAN_ASYNC_GETSET_TYPE, WWAN_ASYNC_GETSET_TYPE, WWAN_ASYNC_GETSET_TYPE enumeration [Network Drivers Starting with Windows Vista], WWAN_ASYNC_GETSET_TYPE_MAX, WwanAsyncAuthChallenge, WwanAsyncGetConnect, WwanAsyncGetDeviceCaps, WwanAsyncGetDeviceServiceCommand get request., WwanAsyncGetDeviceServices, WwanAsyncGetHomeProvider, WwanAsyncGetPacketService, WwanAsyncGetPin, WwanAsyncGetPinEx get request., WwanAsyncGetPinList, WwanAsyncGetPreferredProviders, WwanAsyncGetProvisionedContexts, WwanAsyncGetRadioState, WwanAsyncGetReadyInfo, WwanAsyncGetRegisterState, WwanAsyncGetSignalState, WwanAsyncGetSmsConfiguration, WwanAsyncGetVisibleProviders, WwanAsyncSetConnect, WwanAsyncSetDeviceServiceCommand, WwanAsyncSetHomeProvider, WwanAsyncSetPacketService, WwanAsyncSetPin, WwanAsyncSetPinEx, WwanAsyncSetPreferredProviders, WwanAsyncSetProfileIndex, WwanAsyncSetProvisionedContext, WwanAsyncSetRadioState, WwanAsyncSetRegisterState, WwanAsyncSetServiceActivation, WwanAsyncSetSignalState, WwanAsyncSetSmsConfiguration, WwanAsyncSetVendorSpecific, WwanAsyncSmsDelete, WwanAsyncSmsRead, WwanAsyncSmsSend, WwanAsyncSmsStatus, WwanAsyncSubscribeDeviceServiceEvents, WwanAsyncUssdRequest, _WWAN_ASYNC_GETSET_TYPE, netvista.wwan_async_getset_type, wwan/WWAN_ASYNC_GETSET_TYPE, wwan/WWAN_ASYNC_GETSET_TYPE_MAX, wwan/WwanAsyncAuthChallenge, wwan/WwanAsyncGetConnect, wwan/WwanAsyncGetDeviceCaps, wwan/WwanAsyncGetDeviceServiceCommand get request., wwan/WwanAsyncGetDeviceServices, wwan/WwanAsyncGetHomeProvider, wwan/WwanAsyncGetPacketService, wwan/WwanAsyncGetPin, wwan/WwanAsyncGetPinEx get request., wwan/WwanAsyncGetPinList, wwan/WwanAsyncGetPreferredProviders, wwan/WwanAsyncGetProvisionedContexts, wwan/WwanAsyncGetRadioState, wwan/WwanAsyncGetReadyInfo, wwan/WwanAsyncGetRegisterState, wwan/WwanAsyncGetSignalState, wwan/WwanAsyncGetSmsConfiguration, wwan/WwanAsyncGetVisibleProviders, wwan/WwanAsyncSetConnect, wwan/WwanAsyncSetDeviceServiceCommand, wwan/WwanAsyncSetHomeProvider, wwan/WwanAsyncSetPacketService, wwan/WwanAsyncSetPin, wwan/WwanAsyncSetPinEx, wwan/WwanAsyncSetPreferredProviders, wwan/WwanAsyncSetProfileIndex, wwan/WwanAsyncSetProvisionedContext, wwan/WwanAsyncSetRadioState, wwan/WwanAsyncSetRegisterState, wwan/WwanAsyncSetServiceActivation, wwan/WwanAsyncSetSignalState, wwan/WwanAsyncSetSmsConfiguration, wwan/WwanAsyncSetVendorSpecific, wwan/WwanAsyncSmsDelete, wwan/WwanAsyncSmsRead, wwan/WwanAsyncSmsSend, wwan/WwanAsyncSmsStatus, wwan/WwanAsyncSubscribeDeviceServiceEvents, wwan/WwanAsyncUssdRequest"
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_ASYNC_GETSET_TYPE
product:
- Windows
targetos: Windows
req.typenames: WWAN_ASYNC_GETSET_TYPE, *PWWAN_ASYNC_GETSET_TYPE
---

# _WWAN_ASYNC_GETSET_TYPE enumeration


## -description


The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.


## -enum-fields




### -field WwanAsyncGetDeviceCaps

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569824">OID_WWAN_DEVICE_CAPS</a> get request.


### -field WwanAsyncGetReadyInfo

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569833">OID_WWAN_READY_INFO</a> get request.


### -field WwanAsyncGetRadioState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569832">OID_WWAN_RADIO_STATE</a> get request.


### -field WwanAsyncSetRadioState

Asynchronous [OID_WWAN_RADIO_STATE](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-radio-state) set request.


### -field WwanAsyncGetPin

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569828">OID_WWAN_PIN</a> get request.


### -field WwanAsyncSetPin

Asynchronous [OID_WWAN_PIN](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin) set request.


### -field WwanAsyncGetPinList

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569829">OID_WWAN_PIN_LIST</a> get request.


### -field WwanAsyncGetHomeProvider

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569826">OID_WWAN_HOME_PROVIDER</a> get request.


### -field WwanAsyncSetHomeProvider

Asynchronous [OID_WWAN_HOME_PROVIDER](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-home-provider) set request.


### -field WwanAsyncGetPreferredProviders

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a> get request.


### -field WwanAsyncSetPreferredProviders

Asynchronous [OID_WWAN_PREFERRED_PROVIDERS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-preferred-providers) set request.


### -field WwanAsyncGetVisibleProviders

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a> get request.


### -field WwanAsyncGetRegisterState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569834">OID_WWAN_REGISTER_STATE</a> get request.


### -field WwanAsyncSetRegisterState

Asynchronous [OID_WWAN_REGISTER_STATE](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-register-state) set request.


### -field WwanAsyncGetPacketService

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569827">OID_WWAN_PACKET_SERVICE</a> get request.


### -field WwanAsyncSetPacketService

Asynchronous [OID_WWAN_PACKET_SERVICE](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-packet-service) set request.


### -field WwanAsyncGetSignalState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569836">OID_WWAN_SIGNAL_STATE</a> get request.


### -field WwanAsyncSetSignalState

Asynchronous [OID_WWAN_SIGNAL_STATE](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-signal-state) set request.


### -field WwanAsyncGetConnect

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569823">OID_WWAN_CONNECT</a> get request.


### -field WwanAsyncSetConnect

Asynchronous [OID_WWAN_CONNECT](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-connect) set request.


### -field WwanAsyncGetProvisionedContexts

Asynchronous <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">OID_WWAN_PROVISIONED_CONTEXTS</a> get request.


### -field WwanAsyncSetProvisionedContext

Asynchronous [OID_WWAN_PROVISIONED_CONTEXTS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-provisioned-contexts) set request.


### -field WwanAsyncSetServiceActivation

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569835">OID_WWAN_SERVICE_ACTIVATION</a> set request.


### -field WwanAsyncGetSmsConfiguration

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569837">OID_WWAN_SMS_CONFIGURATION</a> get request.


### -field WwanAsyncSetSmsConfiguration

Asynchronous [OID_WWAN_SMS_CONFIGURATION](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sms-configuration) set request.


### -field WwanAsyncSmsRead

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569839">OID_WWAN_SMS_READ</a> get request.



### -field WwanAsyncSmsSend

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569840">OID_WWAN_SMS_SEND</a> set request.



### -field WwanAsyncSmsDelete

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569838">OID_WWAN_SMS_DELETE</a> set request.



### -field WwanAsyncSmsStatus

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569841">OID_WWAN_SMS_STATUS</a> query request.



### -field WwanAsyncSetVendorSpecific

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569842">OID_WWAN_VENDOR_SPECIFIC</a> set request.



### -field WwanAsyncSetProfileIndex

Reserved.


### -field WwanAsyncGetDeviceServices

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440093">OID_WWAN_DEVICE_SERVICES</a> get request.


### -field WwanAsyncSubscribeDeviceServiceEvents

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a> set request.



### -field WwanAsyncAuthChallenge

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440092">OID_WWAN_AUTH_CHALLENGE</a> query request.



### -field WwanAsyncUssdRequest

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440100">OID_WWAN_USSD</a> set request.



### -field WwanAsyncSetPinEx

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440095">OID_WWAN_PIN_EX</a> set request.


### -field WwanAsyncGetPinEx

Asynchronous [OID_WWAN_PIN_EX](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin-ex) get request.

### -field WwanAsyncGetDeviceServiceCommand

Asynchronous [OID_WWAN_DEVICE_SERVICE_COMMAND](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-service-command) get request.

### -field WwanAsyncSetDeviceServiceCommand

Asynchronous [OID_WWAN_DEVICE_SERVICE_COMMAND](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-service-command) set request.


### -field WwanAsyncQueryDeviceServiceSupportedCommands

Asynchronous [OID_WWAN_DEVICE_SERVICES](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-services)

### -field WwanAsyncGetPreferredMultiCarrierProviders

Asynchronous [OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-preferred-multicarrier-providers) get request.

### -field WwanAsyncSetPreferredMultiCarrierProviders

Asynchronous [OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-preferred-multicarrier-providers) set request.

### -field WwanAsyncSetDeviceServiceSession

Asynchronous [OID_WWAN_DEVICE_SERVICE_SESSION](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-service-session) set request.


### -field WwanAsyncWriteDeviceServiceSession

Asynchronous [OID_WWAN_DEVICE_SERVICE_SESSION_WRITE](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-service-session-write) set request.


### -field WwanAsyncSetNetworkIdleHint

Asynchronous [OID_WWAN_NETWORK_IDLE_HINT](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-network-idle-hint) set request.


### -field WwanAsyncSetPreshutdown

Asynchronous [OID_WWAN_PRESHUTDOWN](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-preshutdown) set request.

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

Asynchronous [OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config) get request.

### -field WwanAsyncSetSarConfig

Asynchronous [OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config) set request.


### -field WwanAsyncGetSarTransmissionStatus

Asynchronous [OID_WWAN_SAR_TRANSMISSION_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-transmission-status) get request.


### -field WwanAsyncSetSarTransmissionStatus

Asynchronous [OID_WWAN_SAR_TRANSMISSION_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-transmission-status) set request.


### -field WwanAsyncGetNetworkBlacklist

Asynchronous [OID_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-network-blacklist) get request.


### -field WwanAsyncSetNetworkBlacklist

Asynchronous [OID_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-network-blacklist) set request.


### -field WwanAsyncGetLteAttachConfig

Asynchronous [OID_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-config) get request.


### -field WwanAsyncSetLteAttachConfig

Asynchronous [OID_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-config) set request.


### -field WwanAsyncGetLteAttachStatus

Asynchronous [OID_WWAN_LTE_ATTACH_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-status) get request.


### -field WwanAsyncSetLteAttachStatus

Asynchronous [OID_WWAN_LTE_ATTACH_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-status) set request.

### -field WwanAsyncGetSysCap

Asynchronous [OID_WWAN_SYS_CAPS_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sys-caps) get request.

### -field WwanAsyncGetDeviceCapsEx

Asynchronous [OID_WWAN_DEVICE_CAPS_EX](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-caps-ex) get request.

### -field WwanAsyncGetUiccSlotMapping

Asynchronous [OID_WWAN_DEVICE_SLOT_MAPPING_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-slot-mappings) get request.

### -field WwanAsyncSetUiccSlotMapping

Asynchronous [OID_WWAN_DEVICE_SLOT_MAPPING_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-slot-mappings) set request.

### -field WwanAsyncGetUiccSlotInfo

Asynchronous [OID_WWAN_SLOT_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-slot-info-status) get request.


### -field WwanAsyncGetModemConfigInfo

Asynchronous [OID_WWAN_MODEM_CONFIG_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-config-info) get request.

### -field WwanAsyncGetPcoStatus

Asynchronous [OID_WWAN_PCO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pco) get request.

### -field WwanAsyncUiccGetReset

Asynchronous [OID_WWAN_UICC_RESET](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-reset) get request.

### -field WwanAsyncUiccSetReset

Asynchronous [OID_WWAN_UICC_RESET](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-reset) set request.

### -field WwanAsyncSetDeviceReset

Asynchronous [OID_WWAN_DEVICE_RESET](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-reset) set request.

### -field WwanAsyncGetCellInfo

Asynchronous [OID_WWAN_BASE_STATIONS_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-base-stations-info) get request.

### -field WwanAsyncGetMPDP

Asynchronous [OID_WWAN_MPDP](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-mpdp) get request.

### -field WwanAsyncSetMPDP

Asynchronous [OID_WWAN_MPDP](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-mpdp) set request.

### -field WWAN_ASYNC_GETSET_TYPE_MAX

The maximum number of entries in the **WWAN_ASYNC_GETSET_TYPE** enumeration.


## -see-also




<a href="https://msdn.microsoft.com/922b6b55-c332-4721-bbd1-571b0e154df3">MB Data Model</a>
 

 

