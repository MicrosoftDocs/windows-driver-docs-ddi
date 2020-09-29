---
UID: NS:wlanihvtypes._DOT11EXT_IHV_PARAMS
title: _DOT11EXT_IHV_PARAMS (wlanihvtypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_params.htm
tech.root: netvista
ms.assetid: 1264bfe7-3ab6-4ba0-aa41-cf81bc9bb687
ms.date: 02/16/2018
keywords: ["DOT11EXT_IHV_PARAMS structure"]
ms.keywords: "*PDOT11EXT_IHV_PARAMS, DOT11EXT_IHV_PARAMS, DOT11EXT_IHV_PARAMS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_90966964-74cc-4ff7-ae77-2807ab20d869.xml, PDOT11EXT_IHV_PARAMS, PDOT11EXT_IHV_PARAMS structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_PARAMS, netvista.dot11ext_ihv_params, wlanihvtypes/DOT11EXT_IHV_PARAMS, wlanihvtypes/PDOT11EXT_IHV_PARAMS"
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
targetos: Windows
req.typenames: DOT11EXT_IHV_PARAMS, *PDOT11EXT_IHV_PARAMS
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11EXT_IHV_PARAMS
 - wlanihvtypes/_DOT11EXT_IHV_PARAMS
 - PDOT11EXT_IHV_PARAMS
 - wlanihvtypes/PDOT11EXT_IHV_PARAMS
 - DOT11EXT_IHV_PARAMS
 - wlanihvtypes/DOT11EXT_IHV_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihvtypes.h
api_name:
 - DOT11EXT_IHV_PARAMS
---

# _DOT11EXT_IHV_PARAMS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_PARAMS structure defines the parameters associated with an IHV profile.

## -struct-fields

### -field dot11ExtIhvProfileParams

A
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure that specifies general parameters of a basic service set
     (BSS) network with which a network profile will be applied.

### -field wstrProfileName

A string that defines the IHV profile name.

### -field dwProfileTypeFlags

The flags associated with this IHV profile type.

### -field interfaceGuid

The globally unique identifier (GUID) for the wireless LAN (WLAN) adapter.


The operating system passes the GUID and other data related to the WLAN adapter through the
     <i>pDot11Adapter</i> parameter of the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">
     Dot11ExtIhvInitAdapter</a> function, which the operating system calls when it detects the arrival of
     the WLAN adapter. For more information about this operation, see
     <a href="/windows/win32/api/l2cmn/ns-l2cmn-l2_notification_data">802.11 WLAN Adapter
     Arrival</a>.

## -syntax

```cpp
typedef struct _DOT11EXT_IHV_PARAMS {
  DOT11EXT_IHV_PROFILE_PARAMS dot11ExtIhvProfileParams;
  WCHAR                       wstrProfileName[MS_MAX_PROFILE_NAME_LENGTH];
  DWORD                       dwProfileTypeFlags;
  GUID                        interfaceGuid;
} DOT11EXT_IHV_PARAMS, *PDOT11EXT_IHV_PARAMS;
```

## -see-also

<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>