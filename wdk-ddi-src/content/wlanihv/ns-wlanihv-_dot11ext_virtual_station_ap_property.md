---
UID: NS:wlanihv._DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
title: _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_virtual_station_ap_property.htm
tech.root: netvista
ms.assetid: b6edad03-63fc-4a27-b999-9014d3735861
ms.date: 02/16/2018
keywords: ["DOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure"]
ms.keywords: "*PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY, DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, DOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_13a72b1b-41e4-4651-a4d5-a120a628defd.xml, PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY, PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, netvista.dot11ext_virtual_station_ap_property, wlanihv/DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, wlanihv/PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.typenames: DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, *PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
 - wlanihv/_DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
 - PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY
 - wlanihv/PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY
 - DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
 - wlanihv/DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihv.h
api_name:
 - DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
---

# _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure specifies the properties of an access point (AP)
  hosted on a virtual 802.11 station.

## -struct-fields

### -field dot11SSID

A
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a> structure that contains the service
     set identifier (SSID) used by the virtual station AP.

### -field dot11AuthAlgo

A
     <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a> structure that
     contains the authentication algorithm used by the virtual station AP.

### -field dot11CipherAlgo

A
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> structure that
     contains the cipher algorithm used by the virtual station AP.

### -field bIsPassPhrase

A Boolean value that indicates how the operating system should interpret the value of the
     <b>ucKeyData</b> member. For more information, see the following Remarks section.

### -field dwKeyLength

The length, in bytes, of the useful part of the
     <b>ucKeyData</b> member. For more information, see the following Remarks section.

### -field ucKeyData

A UCHAR value that specifies the key used by the virtual station AP's Preshared Keys (PSK)
     authentication algorithm. For more information, see the following Remarks section.

## -syntax

```cpp
typedef struct _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY {
  DOT11_SSID             dot11SSID;
  DOT11_AUTH_ALGORITHM   dot11AuthAlgo;
  DOT11_CIPHER_ALGORITHM dot11CipherAlgo;
  BOOL                   bIsPassPhrase;
  DWORD                  dwKeyLength;
  UCHAR                  ucKeyData[DOT11EXT_PSK_MAX_LENGTH];
} DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, *PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY;
```

## -remarks

The operating system uses the following logic to interpret the value of the
    <b>ucKeyData</b> member:

<ul>
<li>If
     <b>bIsPassPhrase</b> = <b>FALSE</b>,
     <ul>
<li>If
      <b>dwKeyLength</b> = 32,
      <b>ucKeyData</b> is interpreted as binary data.</li>
<li>If
      <b>dwKeyLength</b> = 64,
      <b>ucKeyData</b> is interpreted as 32 hexadecimal values.</li>
<li>If
      <b>dwKeyLength</b> is not equal to 32 or 64, the operating system ignores the call and returns an
      error.</li>
</ul>
</li>
<li>
If
      <b>bIsPassPhrase</b> = <b>TRUE</b>,
      <b>ucKeyData</b> is interpreted as a pass phrase, and the buffer must be NULL terminated. In this case,
      <b>dwKeyLength</b> should have a value that equals 1 plus the length of the key string.

</li>
</ul>

## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>