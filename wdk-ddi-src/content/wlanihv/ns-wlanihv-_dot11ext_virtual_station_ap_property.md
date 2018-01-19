---
UID: NS:wlanihv._DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
title: _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_virtual_station_ap_property.htm
old-project: netvista
ms.assetid: b6edad03-63fc-4a27-b999-9014d3735861
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, *PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY, DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
req.alt-loc: wlanihv.h
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
req.typenames: *PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY, DOT11EXT_VIRTUAL_STATION_AP_PROPERTY
req.product: Windows 10 or later.
---

# _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure



## -description

## -syntax

````
typedef struct _DOT11EXT_VIRTUAL_STATION_AP_PROPERTY {
  DOT11_SSID             dot11SSID;
  DOT11_AUTH_ALGORITHM   dot11AuthAlgo;
  DOT11_CIPHER_ALGORITHM dot11CipherAlgo;
  BOOL                   bIsPassPhrase;
  DWORD                  dwKeyLength;
  UCHAR                  ucKeyData[DOT11EXT_PSK_MAX_LENGTH];
} DOT11EXT_VIRTUAL_STATION_AP_PROPERTY, *PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY;
````


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


## -remarks
The operating system uses the following logic to interpret the value of the 
    <b>ucKeyData</b> member:

If 
      <b>bIsPassPhrase</b> = <b>TRUE</b>, 
      <b>ucKeyData</b> is interpreted as a pass phrase, and the buffer must be NULL terminated. In this case, 
      <b>dwKeyLength</b> should have a value that equals 1 plus the length of the key string.


## -see-also
<dl>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>
</dt>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_VIRTUAL_STATION_AP_PROPERTY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

