---
UID: NS:wlanihvtypes._DOT11EXT_IHV_PROFILE_PARAMS
title: _DOT11EXT_IHV_PROFILE_PARAMS (wlanihvtypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_profile_params.htm
tech.root: netvista
ms.assetid: 9bf4b27c-3cf0-45a0-9e56-b01ad1ba6b19
ms.date: 02/16/2018
keywords: ["DOT11EXT_IHV_PROFILE_PARAMS structure"]
ms.keywords: "*PDOT11EXT_IHV_PROFILE_PARAMS, DOT11EXT_IHV_PROFILE_PARAMS, DOT11EXT_IHV_PROFILE_PARAMS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_3fe01c80-477b-4851-8b7e-4d4540cc22b6.xml, PDOT11EXT_IHV_PROFILE_PARAMS, PDOT11EXT_IHV_PROFILE_PARAMS structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_PROFILE_PARAMS, netvista.dot11ext_ihv_profile_params, wlanihvtypes/DOT11EXT_IHV_PROFILE_PARAMS, wlanihvtypes/PDOT11EXT_IHV_PROFILE_PARAMS"
f1_keywords:
 - "wlanihvtypes/DOT11EXT_IHV_PROFILE_PARAMS"
 - "DOT11EXT_IHV_PROFILE_PARAMS"
req.header: wlanihvtypes.h
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
- wlanihvtypes.h
api_name:
- DOT11EXT_IHV_PROFILE_PARAMS
targetos: Windows
req.typenames: DOT11EXT_IHV_PROFILE_PARAMS, *PDOT11EXT_IHV_PROFILE_PARAMS
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_PROFILE_PARAMS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_PROFILE_PARAMS structure specifies the general parameters of a basic service set
  (BSS) network with which a network profile will be applied.


## -syntax


```cpp
typedef struct _DOT11EXT_IHV_PROFILE_PARAMS {
  PDOT11EXT_IHV_SSID_LIST    pSsidList;
  DOT11_BSS_TYPE             BssType;
  PDOT11_MSSECURITY_SETTINGS pMSSecuritySettings;
} DOT11EXT_IHV_PROFILE_PARAMS, *PDOT11EXT_IHV_PROFILE_PARAMS;
```


## -struct-fields




### -field pSsidList

A pointer to the list of service set identifiers (SSIDs) of the basic service set (BSS) network.
     The
     <b>pSsidList</b> member is formatted as a pointer to a
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_ssid_list.md">
     DOT11EXT_IHV_SSID_LIST</a> structure.


### -field BssType

The type of the BSS network. The
     <b>BssType</b> member contains a value defined for the
     <a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a> enumeration.


### -field pMSSecuritySettings

A pointer to a
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11_mssecurity_settings.md">
     DOT11_MSSECURITY_SETTINGS</a> structure that defines Microsoft security settings in the Microsoft
     802.1X implementation.


## -remarks



The operating system passes a pointer to a DOT11EXT_IHV_PROFILE_PARAMS structure as a parameter to any
    IHV handler function that processes the IHV-defined fragments of connectivity and security profiles. For
    more information, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
    Functions</a>.

Although the IHV handler function cannot access the entire network profile, the function can access
    the general attributes of the profile through the DOT11EXT_IHV_PROFILE_PARAMS structure.




## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_capability_match.md">
   Dot11ExtIhvPerformCapabilityMatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff553763(v=vs.85)">
   IDot11ExtUIProperty::Dot11ExtUIPropertySetDisplayInfo</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_validate_profile.md">Dot11ExtIhvValidateProfile</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_ssid_list.md">DOT11EXT_IHV_SSID_LIST</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11_mssecurity_settings.md">DOT11_MSSECURITY_SETTINGS</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
   Dot11ExtIhvCreateDiscoveryProfiles</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff553752(v=vs.85)">
   IDot11ExtUIProperty::Dot11ExtUIPropertyGetDisplayInfo</a>



 

 


