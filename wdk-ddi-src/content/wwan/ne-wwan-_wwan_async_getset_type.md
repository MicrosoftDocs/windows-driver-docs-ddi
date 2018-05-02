---
UID: NE:wwan._WWAN_ASYNC_GETSET_TYPE
title: "_WWAN_ASYNC_GETSET_TYPE"
author: windows-driver-content
description: The WWAN_ASYNC_GETSET_TYPE enumeration lists the different asynchronous OID get/set requests.
old-location: netvista\wwan_async_getset_type.htm
old-project: netvista
ms.assetid: 2FECDA17-7B38-4636-AFAF-D923AECFAF68
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_ASYNC_GETSET_TYPE, WWAN_ASYNC_GETSET_TYPE, WWAN_ASYNC_GETSET_TYPE enumeration [Network Drivers Starting with Windows Vista], WWAN_ASYNC_GETSET_TYPE_MAX, WwanAsyncAuthChallenge, WwanAsyncGetConnect, WwanAsyncGetDeviceCaps, WwanAsyncGetDeviceServiceCommand get request., WwanAsyncGetDeviceServices, WwanAsyncGetHomeProvider, WwanAsyncGetPacketService, WwanAsyncGetPin, WwanAsyncGetPinEx get request., WwanAsyncGetPinList, WwanAsyncGetPreferredProviders, WwanAsyncGetProvisionedContexts, WwanAsyncGetRadioState, WwanAsyncGetReadyInfo, WwanAsyncGetRegisterState, WwanAsyncGetSignalState, WwanAsyncGetSmsConfiguration, WwanAsyncGetVisibleProviders, WwanAsyncSetConnect, WwanAsyncSetDeviceServiceCommand, WwanAsyncSetHomeProvider, WwanAsyncSetPacketService, WwanAsyncSetPin, WwanAsyncSetPinEx, WwanAsyncSetPreferredProviders, WwanAsyncSetProfileIndex, WwanAsyncSetProvisionedContext, WwanAsyncSetRadioState, WwanAsyncSetRegisterState, WwanAsyncSetServiceActivation, WwanAsyncSetSignalState, WwanAsyncSetSmsConfiguration, WwanAsyncSetVendorSpecific, WwanAsyncSmsDelete, WwanAsyncSmsRead, WwanAsyncSmsSend, WwanAsyncSmsStatus, WwanAsyncSubscribeDeviceServiceEvents, WwanAsyncUssdRequest, _WWAN_ASYNC_GETSET_TYPE, netvista.wwan_async_getset_type, wwan/WWAN_ASYNC_GETSET_TYPE, wwan/WWAN_ASYNC_GETSET_TYPE_MAX, wwan/WwanAsyncAuthChallenge, wwan/WwanAsyncGetConnect, wwan/WwanAsyncGetDeviceCaps, wwan/WwanAsyncGetDeviceServiceCommand get request., wwan/WwanAsyncGetDeviceServices, wwan/WwanAsyncGetHomeProvider, wwan/WwanAsyncGetPacketService, wwan/WwanAsyncGetPin, wwan/WwanAsyncGetPinEx get request., wwan/WwanAsyncGetPinList, wwan/WwanAsyncGetPreferredProviders, wwan/WwanAsyncGetProvisionedContexts, wwan/WwanAsyncGetRadioState, wwan/WwanAsyncGetReadyInfo, wwan/WwanAsyncGetRegisterState, wwan/WwanAsyncGetSignalState, wwan/WwanAsyncGetSmsConfiguration, wwan/WwanAsyncGetVisibleProviders, wwan/WwanAsyncSetConnect, wwan/WwanAsyncSetDeviceServiceCommand, wwan/WwanAsyncSetHomeProvider, wwan/WwanAsyncSetPacketService, wwan/WwanAsyncSetPin, wwan/WwanAsyncSetPinEx, wwan/WwanAsyncSetPreferredProviders, wwan/WwanAsyncSetProfileIndex, wwan/WwanAsyncSetProvisionedContext, wwan/WwanAsyncSetRadioState, wwan/WwanAsyncSetRegisterState, wwan/WwanAsyncSetServiceActivation, wwan/WwanAsyncSetSignalState, wwan/WwanAsyncSetSmsConfiguration, wwan/WwanAsyncSetVendorSpecific, wwan/WwanAsyncSmsDelete, wwan/WwanAsyncSmsRead, wwan/WwanAsyncSmsSend, wwan/WwanAsyncSmsStatus, wwan/WwanAsyncSubscribeDeviceServiceEvents, wwan/WwanAsyncUssdRequest"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
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

Asynchronous OID_WWAN_RADIO_STATE set request.


### -field WwanAsyncGetPin

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569828">OID_WWAN_PIN</a> get request.


### -field WwanAsyncSetPin

Asynchronous OID_WWAN_PIN set request.


### -field WwanAsyncGetPinList

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569829">OID_WWAN_PIN_LIST</a> get request.


### -field WwanAsyncGetHomeProvider

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569826">OID_WWAN_HOME_PROVIDER</a> get request.


### -field WwanAsyncSetHomeProvider

Asynchronous OID_WWAN_HOME_PROVIDER set request.


### -field WwanAsyncGetPreferredProviders

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a> get request.


### -field WwanAsyncSetPreferredProviders

Asynchronous OID_WWAN_PREFERRED_PROVIDERS set request.


### -field WwanAsyncGetVisibleProviders

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a> get request.


### -field WwanAsyncGetRegisterState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569834">OID_WWAN_REGISTER_STATE</a> get request.


### -field WwanAsyncSetRegisterState

Asynchronous OID_WWAN_REGISTER_STATE set request.


### -field WwanAsyncGetPacketService

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569827">OID_WWAN_PACKET_SERVICE</a> get request.


### -field WwanAsyncSetPacketService

Asynchronous OID_WWAN_PACKET_SERVICE set request.


### -field WwanAsyncGetSignalState

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569836">OID_WWAN_SIGNAL_STATE</a> get request.


### -field WwanAsyncSetSignalState

Asynchronous OID_WWAN_SIGNAL_STATE set request.


### -field WwanAsyncGetConnect

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569823">OID_WWAN_CONNECT</a> get request.


### -field WwanAsyncSetConnect

Asynchronous OID_WWAN_CONNECT set request.


### -field WwanAsyncGetProvisionedContexts

Asynchronous <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">OID_WWAN_PROVISIONED_CONTEXTS</a> get request.


### -field WwanAsyncSetProvisionedContext

Asynchronous OID_WWAN_PROVISIONED_CONTEXTS set request.


### -field WwanAsyncSetServiceActivation

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569835">OID_WWAN_SERVICE_ACTIVATION</a> set request.


### -field WwanAsyncGetSmsConfiguration

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569837">OID_WWAN_SMS_CONFIGURATION</a> get request.


### -field WwanAsyncSetSmsConfiguration

Asynchronous OID_WWAN_SMS_CONFIGURATION set request.


### -field WwanAsyncSmsRead

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569839">OID_WWAN_SMS_READ</a>



### -field WwanAsyncSmsSend

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569840">OID_WWAN_SMS_SEND</a>



### -field WwanAsyncSmsDelete

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569838">OID_WWAN_SMS_DELETE</a>



### -field WwanAsyncSmsStatus

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569841">OID_WWAN_SMS_STATUS</a>



### -field WwanAsyncSetVendorSpecific

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/ff569842">OID_WWAN_VENDOR_SPECIFIC</a>



### -field WwanAsyncSetProfileIndex

Reserved.


### -field WwanAsyncGetDeviceServices

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440093">OID_WWAN_DEVICE_SERVICES</a> get request.


### -field WwanAsyncSubscribeDeviceServiceEvents

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a>



### -field WwanAsyncAuthChallenge

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440092">OID_WWAN_AUTH_CHALLENGE</a>



### -field WwanAsyncUssdRequest

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440100">OID_WWAN_USSD</a>



### -field WwanAsyncSetPinEx

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440095">OID_WWAN_PIN_EX</a> set request.


### -field WwanAsyncGetPinEx


### -field WwanAsyncGetDeviceServiceCommand


### -field WwanAsyncSetDeviceServiceCommand

Asynchronous OID_WWAN_DEVICE_SERVICE_COMMAND set request.


### -field WwanAsyncQueryDeviceServiceSupportedCommands


### -field WwanAsyncGetPreferredMultiCarrierProviders


### -field WwanAsyncSetPreferredMultiCarrierProviders


### -field WwanAsyncSetDeviceServiceSession


### -field WwanAsyncWriteDeviceServiceSession


### -field WwanAsyncSetNetworkIdleHint


### -field WwanAsyncSetPreshutdown


### -field WwanAsyncGetAtr


### -field WwanAsyncUiccOpenChannel


### -field WwanAsyncUiccCloseChannel


### -field WwanAsyncUiccSendApdu


### -field WwanAsyncUiccGetTerminalCapability


### -field WwanAsyncUiccSetTerminalCapability


### -field WwanAsyncGetPsMediaConfig


### -field WwanAsyncSetPsMediaConfig


### -field WwanAsyncGetSarConfig


### -field WwanAsyncSetSarConfig


### -field WwanAsyncGetSarTransmissionStatus


### -field WwanAsyncSetSarTransmissionStatus


### -field WwanAsyncGetNetworkBlacklist


### -field WwanAsyncSetNetworkBlacklist


### -field WwanAsyncGetLteAttachConfig


### -field WwanAsyncSetLteAttachConfig


### -field WwanAsyncGetLteAttachStatus


### -field WwanAsyncSetLteAttachStatus


### -field WwanAsyncGetProvisionedContextsV2


### -field WwanAsyncSetProvisionedContextV2


### -field WwanAsyncGetSysCap


### -field WwanAsyncGetDeviceCapsEx


### -field WwanAsyncGetUiccSlotMapping


### -field WwanAsyncSetUiccSlotMapping


### -field WwanAsyncGetUiccSlotInfo


### -field WwanAsyncGetModemConfigInfo


### -field WwanAsyncGetPcoStatus


### -field WwanAsyncUiccGetReset


### -field WwanAsyncUiccSetReset


### -field WwanAsyncSetDeviceReset


### -field WwanAsyncGetCellInfo


### -field WWAN_ASYNC_GETSET_TYPE_MAX

The maximum number of entries in the WWAN_ASYNC_GETSET_TYPE enumeration.


##### - WwanAsyncGetDeviceServiceCommand get request.

Asynchronous <a href="https://msdn.microsoft.com/library/windows/hardware/hh440094">OID_WWAN_DEVICE_SERVICE_COMMAND</a>



##### - WwanAsyncGetPinEx get request.

Asynchronous OID_WWAN_PIN_EX get request.


## -see-also




<a href="https://msdn.microsoft.com/922b6b55-c332-4721-bbd1-571b0e154df3">MB Data Model</a>
 

 

