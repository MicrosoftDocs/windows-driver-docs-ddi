---
UID: NS:wlanihvtypes._DOT11EXT_IHV_SSID_LIST
title: _DOT11EXT_IHV_SSID_LIST (wlanihvtypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_ssid_list.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11EXT_IHV_SSID_LIST structure"]
ms.keywords: "*PDOT11EXT_IHV_SSID_LIST, DOT11EXT_IHV_SSID_LIST, DOT11EXT_IHV_SSID_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_c4e6c252-de57-4173-b6e1-df48dca0404f.xml, PDOT11EXT_IHV_SSID_LIST, PDOT11EXT_IHV_SSID_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_SSID_LIST, netvista.dot11ext_ihv_ssid_list, wlanihvtypes/DOT11EXT_IHV_SSID_LIST, wlanihvtypes/PDOT11EXT_IHV_SSID_LIST"
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
req.typenames: DOT11EXT_IHV_SSID_LIST, *PDOT11EXT_IHV_SSID_LIST
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11EXT_IHV_SSID_LIST
 - wlanihvtypes/_DOT11EXT_IHV_SSID_LIST
 - PDOT11EXT_IHV_SSID_LIST
 - wlanihvtypes/PDOT11EXT_IHV_SSID_LIST
 - DOT11EXT_IHV_SSID_LIST
 - wlanihvtypes/DOT11EXT_IHV_SSID_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihvtypes.h
api_name:
 - _DOT11EXT_IHV_SSID_LIST
 - PDOT11EXT_IHV_SSID_LIST
 - DOT11EXT_IHV_SSID_LIST
---

# _DOT11EXT_IHV_SSID_LIST structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_SSID_LIST structure specifies a list of 802.11 service set identifiers
  (SSIDs).

## -struct-fields

### -field ulCount

The number of SSIDs in the list.

### -field SSIDs

An SSID of type
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>. This is the first SSID in the
     list.

## -syntax

```cpp
typedef struct _DOT11EXT_IHV_SSID_LIST {
  ULONG      ulCount;
  DOT11_SSID SSIDs[1];
} DOT11EXT_IHV_SSID_LIST, *PDOT11EXT_IHV_SSID_LIST;
```

## -remarks

An SSID is a string that identifies a set of interconnected basic service sets (BSSs).

## -see-also

<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>

