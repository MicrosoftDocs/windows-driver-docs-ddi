---
UID: NS:wlanihv._WDIAG_IHV_WLAN_ID
title: _WDIAG_IHV_WLAN_ID
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\wdiag_ihv_wlan_id.htm
old-project: netvista
ms.assetid: 72dc7128-fcbc-4ad8-ac81-e2767ac6ffa2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDIAG_IHV_WLAN_ID, WDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID
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
req.alt-api: WDIAG_IHV_WLAN_ID
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
req.typenames: WDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID
req.product: Windows 10 or later.
---

# _WDIAG_IHV_WLAN_ID structure



## -description

## -syntax

````
typedef struct _WDIAG_IHV_WLAN_ID {
  WCHAR          strProfileName[MS_MAX_PROFILE_NAME_LENGTH];
  DOT11_SSID     Ssid;
  DOT11_BSS_TYPE BssType;
  DWORD          dwFlags;
  DWORD          dwReasonCode;
} WDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID;
````


## -struct-fields

### -field strProfileName

A string that defines the IHV profile name.


### -field Ssid

The service set identifier (SSID) of the basic service set (BSS) network. The 
     <b>Ssid</b> member is of the 
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a> type.


### -field BssType

The type of the BSS network. The 
     <b>BssType</b> member contains a value defined for the 
     <a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a> enumeration.


### -field dwFlags

A flag which, if set to WDIAG_IHV_WLAN_ID_FLAG_SECURITY_ENABLED, indicates that security is
     enabled for this IHV profile. Otherwise, security is not enabled.


### -field dwReasonCode

An error reason code, when available.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>
</dt>
<dt>
<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDIAG_IHV_WLAN_ID structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

