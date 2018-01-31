---
UID: NS:wlanihv._DOT11EXT_APIS
title: "_DOT11EXT_APIS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_apis.htm
old-project: netvista
ms.assetid: d533acbb-eb3b-4c49-a057-9a99faaacfc1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PDOT11EXT_APIS, wlanihv/DOT11EXT_APIS, netvista.dot11ext_apis, DOT11EXT_APIS structure [Network Drivers Starting with Windows Vista], wlanihv/PDOT11EXT_APIS, DOT11EXT_APIS, PDOT11EXT_APIS structure pointer [Network Drivers Starting with Windows Vista], Native_802.11_data_types_27860ed6-1413-4bc6-9cd0-fb4391dff322.xml, *PDOT11EXT_APIS, _DOT11EXT_APIS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wlanihv.h
apiname:
-	DOT11EXT_APIS
product: Windows
targetos: Windows
req.typenames: DOT11EXT_APIS, *PDOT11EXT_APIS
req.product: Windows 10 or later.
---

# _DOT11EXT_APIS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_APIS structure specifies a list of pointers to the IHV Extensibility functions that are
  supported by the operating system.


## -syntax


````
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
````


## -struct-fields





#### - Dot11ExtAllocateBuffer

A pointer to the 
     <mshelp:link keywords="netvista.dot11extallocatebuffer" tabindex="0"><b>
     Dot11ExtAllocateBuffer</b></mshelp:link> function.


#### - Dot11ExtFreeBuffer

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a> function.


#### - Dot11ExtSetProfileCustomUserData

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetprofilecustomuserdata" tabindex="0"><b>
     Dot11ExtSetProfileCustomUserData</b></mshelp:link> function.


#### - Dot11ExtGetProfileCustomUserData

A pointer to the 
     <mshelp:link keywords="netvista.dot11extgetprofilecustomuserdata" tabindex="0"><b>
     Dot11ExtGetProfileCustomUserData</b></mshelp:link> function.


#### - Dot11ExtSetCurrentProfile

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetcurrentprofile" tabindex="0"><b>
     Dot11ExtSetCurrentProfile</b></mshelp:link> function.


#### - Dot11ExtSendUIRequest

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsenduirequest" tabindex="0"><b>
     Dot11ExtSendUIRequest</b></mshelp:link> function.


#### - Dot11ExtPreAssociateCompletion

A pointer to the 
     <mshelp:link keywords="netvista.dot11extpreassociatecompletion" tabindex="0"><b>
     Dot11ExtPreAssociateCompletion</b></mshelp:link> function.


#### - Dot11ExtPostAssociateCompletion

A pointer to the 
     <mshelp:link keywords="netvista.dot11extpostassociatecompletion" tabindex="0"><b>
     Dot11ExtPostAssociateCompletion</b></mshelp:link> function.


#### - Dot11ExtSendNotification

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsendnotification" tabindex="0"><b>
     Dot11ExtSendNotification</b></mshelp:link> function.


#### - Dot11ExtSendPacket

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a> function.


#### - Dot11ExtSetEtherTypeHandling

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetethertypehandling" tabindex="0"><b>
     Dot11ExtSetEtherTypeHandling</b></mshelp:link> function.


#### - Dot11ExtSetAuthAlgorithm

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetauthalgorithm" tabindex="0"><b>
     Dot11ExtSetAuthAlgorithm</b></mshelp:link> function.


#### - Dot11ExtSetUnicastCipherAlgorithm

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetunicastcipheralgorithm" tabindex="0"><b>
     Dot11ExtSetUnicastCipherAlgorithm</b></mshelp:link> function.


#### - Dot11ExtSetMulticastCipherAlgorithm

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetmulticastcipheralgorithm" tabindex="0"><b>
     Dot11ExtSetMulticastCipherAlgorithm</b></mshelp:link> function.


#### - Dot11ExtSetDefaultKey

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetdefaultkey" tabindex="0"><b>
     Dot11ExtSetDefaultKey</b></mshelp:link> function.


#### - Dot11ExtSetKeyMappingKey

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetkeymappingkey" tabindex="0"><b>
     Dot11ExtSetKeyMappingKey</b></mshelp:link> function.


#### - Dot11ExtSetDefaultKeyId

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetdefaultkeyid" tabindex="0"><b>
     Dot11ExtSetDefaultKeyId</b></mshelp:link> function.


#### - Dot11ExtNicSpecificExtension

A pointer to the 
     <mshelp:link keywords="netvista.dot11extnicspecificextension" tabindex="0"><b>
     Dot11ExtNicSpecificExtension</b></mshelp:link> function.


#### - Dot11ExtSetExcludeUnencrypted

A pointer to the 
     <mshelp:link keywords="netvista.dot11extsetexcludeunencrypted" tabindex="0"><b>
     Dot11ExtSetExcludeUnencrypted</b></mshelp:link> function.


#### - Dot11ExtStartOneX

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function.


#### - Dot11ExtStopOneX

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a> function.


#### - Dot11ExtProcessOneXPacket

A pointer to the 
     <mshelp:link keywords="netvista.dot11extprocessonexpacket" tabindex="0"><b>
     Dot11ExtProcessOneXPacket</b></mshelp:link> function.


## -remarks


The IHV Extensibility functions are not statically or dynamically linked to the IHV Extensions DLL.
    Instead, when the operating system calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a> IHV
    handler function, it passes the list of pointers to the IHV Extensibility functions through the 
    <i>pDot11ExtAPI</i> parameter.

All of the function pointers are required and will not be set to <b>NULL</b>.



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">Dot11ExtGetUserData</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_nic_specific_extension.md">Dot11ExtNicSpecificExtension</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key_id.md">Dot11ExtSetDefaultKeyId</a>

<mshelp:link keywords="netvista.native_802_11_ihv_extensibility_functions" tabindex="0">Native 802.11 IHV
   Extensibility Functions</mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>

<mshelp:link keywords="netvista.dot11extsetunicastcipheralgorithm" tabindex="0"><b>
   Dot11ExtSetUnicastCipherAlgorithm</b></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11ext_send_notification.md">Dot11ExtSendNotification</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_key_mapping_key.md">Dot11ExtSetKeyMappingKey</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key.md">Dot11ExtSetDefaultKey</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_auth_algorithm.md">Dot11ExtSetAuthAlgorithm</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>

<mshelp:link keywords="netvista.native_802_11_ihv_handler_functions" tabindex="0">Native 802.11 IHV Handler
   Functions</mshelp:link>

<mshelp:link keywords="netvista.dot11extsetprofilecustomuserdata" tabindex="0"><b>
   Dot11ExtSetProfileCustomUserData</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extpreassociatecompletion" tabindex="0"><b>
   Dot11ExtPreAssociateCompletion</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extpostassociatecompletion" tabindex="0"><b>
   Dot11ExtPostAssociateCompletion</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extsetmulticastcipheralgorithm" tabindex="0"><b>
   Dot11ExtSetMulticastCipherAlgorithm</b></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>

<mshelp:link keywords="netvista.dot11extsetexcludeunencrypted" tabindex="0"><b>
   Dot11ExtSetExcludeUnencrypted</b></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_APIS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

