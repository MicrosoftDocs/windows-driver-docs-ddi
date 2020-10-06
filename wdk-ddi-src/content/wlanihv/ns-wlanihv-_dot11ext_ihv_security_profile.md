---
UID: NS:wlanihv._DOT11EXT_IHV_SECURITY_PROFILE
title: _DOT11EXT_IHV_SECURITY_PROFILE (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_security_profile.htm
tech.root: netvista
ms.assetid: cbfeace3-6492-4011-9ca8-c40ba4f47d22
ms.date: 02/16/2018
keywords: ["DOT11EXT_IHV_SECURITY_PROFILE structure"]
ms.keywords: "*PDOT11EXT_IHV_SECURITY_PROFILE, DOT11EXT_IHV_SECURITY_PROFILE, DOT11EXT_IHV_SECURITY_PROFILE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_7761c811-0068-48d5-8b46-da550a008a9c.xml, PDOT11EXT_IHV_SECURITY_PROFILE, PDOT11EXT_IHV_SECURITY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_SECURITY_PROFILE, netvista.dot11ext_ihv_security_profile, wlanihv/DOT11EXT_IHV_SECURITY_PROFILE, wlanihv/PDOT11EXT_IHV_SECURITY_PROFILE"
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
targetos: Windows
req.typenames: DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11EXT_IHV_SECURITY_PROFILE
 - wlanihv/_DOT11EXT_IHV_SECURITY_PROFILE
 - PDOT11EXT_IHV_SECURITY_PROFILE
 - wlanihv/PDOT11EXT_IHV_SECURITY_PROFILE
 - DOT11EXT_IHV_SECURITY_PROFILE
 - wlanihv/DOT11EXT_IHV_SECURITY_PROFILE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihv.h
api_name:
 - DOT11EXT_IHV_SECURITY_PROFILE
---

# _DOT11EXT_IHV_SECURITY_PROFILE structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_SECURITY_PROFILE structure specifies security settings for the IHV profile.

## -struct-fields

### -field pszXmlFragmentIhvSecurity

A pointer to the string that defines the IHV security profile.

### -field bUseMSOnex

A flag that indicates whether the IHV security profile is using the Microsoft 802.1X
     implementation. If <b>TRUE</b>, the profile uses the Microsoft 802.1X implementation.

## -syntax

```cpp
typedef struct _DOT11EXT_IHV_SECURITY_PROFILE {
  LPWSTR pszXmlFragmentIhvSecurity;
  BOOL   bUseMSOnex;
} DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE;
```