---
UID: NS:wlanihv._DOT11EXT_IHV_DISCOVERY_PROFILE
title: _DOT11EXT_IHV_DISCOVERY_PROFILE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_discovery_profile.htm
tech.root: netvista
ms.assetid: 9044d045-a997-4660-815d-07dad0ac832e
ms.date: 02/16/2018
keywords: ["_DOT11EXT_IHV_DISCOVERY_PROFILE structure"]
ms.keywords: "*PDOT11EXT_IHV_DISCOVERY_PROFILE, DOT11EXT_IHV_DISCOVERY_PROFILE, DOT11EXT_IHV_DISCOVERY_PROFILE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_38fefdc4-fa98-4986-822b-807caa03b205.xml, PDOT11EXT_IHV_DISCOVERY_PROFILE, PDOT11EXT_IHV_DISCOVERY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_DISCOVERY_PROFILE, netvista.dot11ext_ihv_discovery_profile, wlanihv/DOT11EXT_IHV_DISCOVERY_PROFILE, wlanihv/PDOT11EXT_IHV_DISCOVERY_PROFILE"
f1_keywords:
 - "wlanihv/DOT11EXT_IHV_DISCOVERY_PROFILE"
 - "DOT11EXT_IHV_DISCOVERY_PROFILE"
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
- DOT11EXT_IHV_DISCOVERY_PROFILE
targetos: Windows
req.typenames: DOT11EXT_IHV_DISCOVERY_PROFILE, *PDOT11EXT_IHV_DISCOVERY_PROFILE
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_DISCOVERY_PROFILE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_DISCOVERY_PROFILE structure specifies a single IHV discovery profile.


## -syntax


```cpp
typedef struct _DOT11EXT_IHV_DISCOVERY_PROFILE {
  DOT11EXT_IHV_CONNECTIVITY_PROFILE IhvConnectivityProfile;
  DOT11EXT_IHV_SECURITY_PROFILE     IhvSecurityProfile;
} DOT11EXT_IHV_DISCOVERY_PROFILE, *PDOT11EXT_IHV_DISCOVERY_PROFILE;
```


## -struct-fields




### -field IhvConnectivityProfile

The IHV connectivity profile specified by a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure.


### -field IhvSecurityProfile

The IHV security profile specified by a
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure.


## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_connectivity_profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>



 

 


