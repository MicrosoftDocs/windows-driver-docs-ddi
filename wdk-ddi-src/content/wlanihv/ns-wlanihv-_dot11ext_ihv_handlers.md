---
UID: NS:wlanihv._DOT11EXT_IHV_HANDLERS
title: "_DOT11EXT_IHV_HANDLERS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_handlers.htm
old-project: netvista
ms.assetid: 6dacd330-45f1-46f8-b2bf-2006c89f664f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11EXT_IHV_HANDLERS, DOT11EXT_IHV_HANDLERS, DOT11EXT_IHV_HANDLERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_e072dcd6-e41c-4c08-b958-9302f62f02c1.xml, PDOT11EXT_IHV_HANDLERS, PDOT11EXT_IHV_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_HANDLERS, netvista.dot11ext_ihv_handlers, wlanihv/DOT11EXT_IHV_HANDLERS, wlanihv/PDOT11EXT_IHV_HANDLERS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wlanihv.h
api_name:
-	DOT11EXT_IHV_HANDLERS
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_HANDLERS, *PDOT11EXT_IHV_HANDLERS
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_HANDLERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_HANDLERS structure specifies a list of pointers to the IHV handler functions
  supported by the IHV Extensions DLL.


## -syntax


````
typedef struct _DOT11EXT_IHV_HANDLERS {
  DOT11EXTIHV_DEINIT_SERVICE            Dot11ExtIhvDeinitService;
  DOT11EXTIHV_INIT_ADAPTER              Dot11ExtIhvInitAdapter;
  DOT11EXTIHV_DEINIT_ADAPTER            Dot11ExtIhvDeinitAdapter;
  DOT11EXTIHV_PERFORM_PRE_ASSOCIATE     Dot11ExtIhvPerformPreAssociate;
  DOT11EXTIHV_ADAPTER_RESET             Dot11ExtIhvAdapterReset;
  DOT11EXTIHV_PERFORM_POST_ASSOCIATE    Dot11ExtIhvPerformPostAssociate;
  DOT11EXTIHV_STOP_POST_ASSOCIATE       Dot11ExtIhvStopPostAssociate;
  DOT11EXTIHV_VALIDATE_PROFILE          Dot11ExtIhvValidateProfile;
  DOT11EXTIHV_PERFORM_CAPABILITY_MATCH  Dot11ExtIhvPerformCapabilityMatch;
  DOT11EXTIHV_CREATE_DISCOVERY_PROFILES Dot11ExtIhvCreateDiscoveryProfiles;
  DOT11EXTIHV_PROCESS_SESSION_CHANGE    Dot11ExtIhvProcessSessionChange;
  DOT11EXTIHV_RECEIVE_INDICATION        Dot11ExtIhvReceiveIndication;
  DOT11EXTIHV_RECEIVE_PACKET            Dot11ExtIhvReceivePacket;
  DOT11EXTIHV_SEND_PACKET_COMPLETION    Dot11ExtIhvSendPacketCompletion;
  DOT11EXTIHV_IS_UI_REQUEST_PENDING     Dot11ExtIhvIsUIRequestPending;
  DOT11EXTIHV_PROCESS_UI_RESPONSE       Dot11ExtIhvProcessUIResponse;
  DOT11EXTIHV_QUERY_UI_REQUEST          Dot11ExtIhvQueryUIRequest;
  DOT11EXTIHV_ONEX_INDICATE_RESULT      Dot11ExtIhvOnexIndicateResult;
  DOT11EXTIHV_CONTROL                   Dot11ExtIhvControl;
} DOT11EXT_IHV_HANDLERS, *PDOT11EXT_IHV_HANDLERS;
````


## -struct-fields




### -field Dot11ExtIhvDeinitService

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_service.md">
     Dot11ExtIhvDeinitService</a> function.


### -field Dot11ExtIhvInitAdapter

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">
     Dot11ExtIhvInitAdapter</a> function.


### -field Dot11ExtIhvDeinitAdapter

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">
     Dot11ExtIhvDeinitAdapter</a> function.


### -field Dot11ExtIhvPerformPreAssociate

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> function.


### -field Dot11ExtIhvAdapterReset

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">
     Dot11ExtIhvAdapterReset</a> function.


### -field Dot11ExtIhvPerformPostAssociate

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
     Dot11ExtIhvPerformPostAssociate</a> function.


### -field Dot11ExtIhvStopPostAssociate

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_stop_post_associate.md">
     Dot11ExtIhvStopPostAssociate</a> function.


### -field Dot11ExtIhvValidateProfile

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_validate_profile.md">
     Dot11ExtIhvValidateProfile</a> function.


### -field Dot11ExtIhvPerformCapabilityMatch

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_capability_match.md">
     Dot11ExtIhvPerformCapabilityMatch</a> function.


### -field Dot11ExtIhvCreateDiscoveryProfiles

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
     Dot11ExtIhvCreateDiscoveryProfiles</a> function.


### -field Dot11ExtIhvProcessSessionChange

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_process_session_change.md">
     Dot11ExtIhvProcessSessionChange</a> function.


### -field Dot11ExtIhvReceiveIndication

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_indication.md">
     Dot11ExtIhvReceiveIndication</a> function.


### -field Dot11ExtIhvReceivePacket

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">
     Dot11ExtIhvReceivePacket</a> function.


### -field Dot11ExtIhvSendPacketCompletion

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_send_packet_completion.md">
     Dot11ExtIhvSendPacketCompletion</a> function.


### -field Dot11ExtIhvIsUIRequestPending

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_is_ui_request_pending.md">
     Dot11ExtIhvIsUIRequestPending</a> function.


### -field Dot11ExtIhvProcessUIResponse

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_process_ui_response.md">
     Dot11ExtIhvProcessUIResponse</a> function.


### -field Dot11ExtIhvQueryUIRequest

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">
     Dot11ExtIhvQueryUIRequest</a> function.


### -field Dot11ExtIhvOnexIndicateResult

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
     Dot11ExtIhvOneXIndicateResult</a> function.


### -field Dot11ExtIhvControl

A pointer to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_control.md">Dot11ExtIhvControl</a> function.


## -remarks



The IHV handler functions are a set of callback functions supported by the IHV Extensions DLL. When
    the operating system calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a> IHV
    handler function, the IHV Extensions DLL returns the list of pointers to the IHV handler functions
    through the 
    <i>pDot11IHVHandlers</i> parameter.

<div class="alert"><b>Note</b>  The operating system resolves the addresses of the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a> and
    
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a> IHV
    handler functions through 
    <b>GetProcAddress</b>. For more information about 
    <b>GetProcAddress</b>, refer to the Microsoft Windows SDK documentation.</div>
<div> </div>
All of the function pointers are required and must not be set to <b>NULL</b>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_validate_profile.md">Dot11ExtIhvValidateProfile</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_indication.md">
   Dot11ExtIhvReceiveIndication</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_stop_post_associate.md">
   Dot11ExtIhvStopPostAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_process_session_change.md">
   Dot11ExtIhvProcessSessionChange</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-extensibility-functions">Native 802.11 IHV
   Extensibility Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
   Dot11ExtIhvCreateDiscoveryProfiles</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">Dot11ExtIhvQueryUIRequest</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_process_ui_response.md">
   Dot11ExtIhvProcessUIResponse</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_control.md">Dot11ExtIhvControl Function</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_capability_match.md">
   Dot11ExtIhvPerformCapabilityMatch</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_is_ui_request_pending.md">
   Dot11ExtIhvIsUIRequestPending</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_service.md">Dot11ExtIhvDeinitService</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_send_packet_completion.md">
   Dot11ExtIhvSendPacketCompletion</a>



 

 


