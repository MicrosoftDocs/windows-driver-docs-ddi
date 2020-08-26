---
UID: NS:wlanihv._DOT11EXT_APIS
title: _DOT11EXT_APIS (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_apis.htm
tech.root: netvista
ms.assetid: d533acbb-eb3b-4c49-a057-9a99faaacfc1
ms.date: 02/16/2018
keywords: ["DOT11EXT_APIS structure"]
ms.keywords: "*PDOT11EXT_APIS, DOT11EXT_APIS, DOT11EXT_APIS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_27860ed6-1413-4bc6-9cd0-fb4391dff322.xml, PDOT11EXT_APIS, PDOT11EXT_APIS structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_APIS, netvista.dot11ext_apis, wlanihv/DOT11EXT_APIS, wlanihv/PDOT11EXT_APIS"
f1_keywords:
 - "wlanihv/DOT11EXT_APIS"
 - "DOT11EXT_APIS"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wlanihv.h
api_name:
- DOT11EXT_APIS
targetos: Windows
req.typenames: DOT11EXT_APIS, *PDOT11EXT_APIS
req.product: Windows 10 or later.
---

# _DOT11EXT_APIS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_APIS structure specifies a list of pointers to the IHV Extensibility functions that are
  supported by the operating system.


## -syntax


```cpp
typedef struct _DOT11EXT_APIS {
  DOT11EXT_ALLOCATE_BUFFER                Dot11ExtAllocateBuffer;
  DOT11EXT_FREE_BUFFER                    Dot11ExtFreeBuffer;
  DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA   Dot11ExtSetProfileCustomUserData;
  DOT11EXT_GET_PROFILE_CUSTOM_USER_DATA   Dot11ExtGetProfileCustomUserData;
  DOT11EXT_SET_CURRENT_PROFILE            Dot11ExtSetCurrentProfile;
  DOT11EXT_SEND_UI_REQUEST                Dot11ExtSendUIRequest;
  DOT11EXT_PRE_ASSOCIATE_COMPLETION       Dot11ExtPreAssociateCompletion;
  DOT11EXT_POST_ASSOCIATE_COMPLETION      Dot11ExtPostAssociateCompletion;
  DOT11EXT_SEND_NOTIFICATION              Dot11ExtSendNotification;
  DOT11EXT_SEND_PACKET                    Dot11ExtSendPacket;
  DOT11EXT_SET_ETHERTYPE_HANDLING         Dot11ExtSetEtherTypeHandling;
  DOT11EXT_SET_AUTH_ALGORITHM             Dot11ExtSetAuthAlgorithm;
  DOT11EXT_SET_UNICAST_CIPHER_ALGORITHM   Dot11ExtSetUnicastCipherAlgorithm;
  DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM Dot11ExtSetMulticastCipherAlgorithm;
  DOT11EXT_SET_DEFAULT_KEY                Dot11ExtSetDefaultKey;
  DOT11EXT_SET_KEY_MAPPING_KEY            Dot11ExtSetKeyMappingKey;
  DOT11EXT_SET_DEFAULT_KEY_ID             Dot11ExtSetDefaultKeyId;
  DOT11EXT_NIC_SPECIFIC_EXTENSION         Dot11ExtNicSpecificExtension;
  DOT11EXT_SET_EXCLUDE_UNENCRYPTED        Dot11ExtSetExcludeUnencrypted;
  DOT11EXT_ONEX_START                     Dot11ExtStartOneX;
  DOT11EXT_ONEX_STOP                      Dot11ExtStopOneX;
  DOT11EXT_PROCESS_ONEX_PACKET            Dot11ExtProcessOneXPacket;
} DOT11EXT_APIS, *PDOT11EXT_APIS;
```


## -struct-fields




### -field Dot11ExtAllocateBuffer

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">
     Dot11ExtAllocateBuffer</a> function.


### -field Dot11ExtFreeBuffer

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a> function.


### -field Dot11ExtSetProfileCustomUserData

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_profile_custom_user_data.md">
     Dot11ExtSetProfileCustomUserData</a> function.


### -field Dot11ExtGetProfileCustomUserData

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">
     Dot11ExtGetProfileCustomUserData</a> function.


### -field Dot11ExtSetCurrentProfile

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">
     Dot11ExtSetCurrentProfile</a> function.


### -field Dot11ExtSendUIRequest

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">
     Dot11ExtSendUIRequest</a> function.


### -field Dot11ExtPreAssociateCompletion

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
     Dot11ExtPreAssociateCompletion</a> function.


### -field Dot11ExtPostAssociateCompletion

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
     Dot11ExtPostAssociateCompletion</a> function.


### -field Dot11ExtSendNotification

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_notification.md">
     Dot11ExtSendNotification</a> function.


### -field Dot11ExtSendPacket

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a> function.


### -field Dot11ExtSetEtherTypeHandling

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">
     Dot11ExtSetEtherTypeHandling</a> function.


### -field Dot11ExtSetAuthAlgorithm

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_auth_algorithm.md">
     Dot11ExtSetAuthAlgorithm</a> function.


### -field Dot11ExtSetUnicastCipherAlgorithm

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_unicast_cipher_algorithm.md">
     Dot11ExtSetUnicastCipherAlgorithm</a> function.


### -field Dot11ExtSetMulticastCipherAlgorithm

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_multicast_cipher_algorithm.md">
     Dot11ExtSetMulticastCipherAlgorithm</a> function.


### -field Dot11ExtSetDefaultKey

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key.md">
     Dot11ExtSetDefaultKey</a> function.


### -field Dot11ExtSetKeyMappingKey

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_key_mapping_key.md">
     Dot11ExtSetKeyMappingKey</a> function.


### -field Dot11ExtSetDefaultKeyId

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key_id.md">
     Dot11ExtSetDefaultKeyId</a> function.


### -field Dot11ExtNicSpecificExtension

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_nic_specific_extension.md">
     Dot11ExtNicSpecificExtension</a> function.


### -field Dot11ExtSetExcludeUnencrypted

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_exclude_unencrypted.md">
     Dot11ExtSetExcludeUnencrypted</a> function.


### -field Dot11ExtStartOneX

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function.


### -field Dot11ExtStopOneX

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a> function.


### -field Dot11ExtProcessSecurityPacket






#### - Dot11ExtProcessOneXPacket

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">
     Dot11ExtProcessOneXPacket</a> function.


## -remarks



The IHV Extensibility functions are not statically or dynamically linked to the IHV Extensions DLL.
    Instead, when the operating system calls the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a> IHV
    handler function, it passes the list of pointers to the IHV Extensibility functions through the
    <i>pDot11ExtAPI</i> parameter.

All of the function pointers are required and will not be set to <b>NULL</b>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key.md">Dot11ExtSetDefaultKey</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">Dot11ExtGetUserData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_profile_custom_user_data.md">
   Dot11ExtSetProfileCustomUserData</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key_id.md">Dot11ExtSetDefaultKeyId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-extensibility-functions">Native 802.11 IHV
   Extensibility Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_exclude_unencrypted.md">
   Dot11ExtSetExcludeUnencrypted</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_key_mapping_key.md">Dot11ExtSetKeyMappingKey</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_unicast_cipher_algorithm.md">
   Dot11ExtSetUnicastCipherAlgorithm</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_multicast_cipher_algorithm.md">
   Dot11ExtSetMulticastCipherAlgorithm</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_nic_specific_extension.md">Dot11ExtNicSpecificExtension</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_auth_algorithm.md">Dot11ExtSetAuthAlgorithm</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_send_notification.md">Dot11ExtSendNotification</a>



 

 


