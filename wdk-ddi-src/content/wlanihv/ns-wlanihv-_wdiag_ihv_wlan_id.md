---
UID: NS:wlanihv._WDIAG_IHV_WLAN_ID
title: "_WDIAG_IHV_WLAN_ID"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\wdiag_ihv_wlan_id.htm
old-project: netvista
ms.assetid: 72dc7128-fcbc-4ad8-ac81-e2767ac6ffa2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWDIAG_IHV_WLAN_ID, Native_802.11_data_types_25565f34-9a6d-4c59-908f-527c1d9a43b1.xml, PWDIAG_IHV_WLAN_ID, PWDIAG_IHV_WLAN_ID structure pointer [Network Drivers Starting with Windows Vista], WDIAG_IHV_WLAN_ID, WDIAG_IHV_WLAN_ID structure [Network Drivers Starting with Windows Vista], _WDIAG_IHV_WLAN_ID, netvista.wdiag_ihv_wlan_id, wlanihv/PWDIAG_IHV_WLAN_ID, wlanihv/WDIAG_IHV_WLAN_ID"
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
-	WDIAG_IHV_WLAN_ID
product: Windows
targetos: Windows
req.typenames: WDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID
req.product: Windows 10 or later.
---

# _WDIAG_IHV_WLAN_ID structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The WDIAG_IHV_WLAN_ID structure specifies an identifier used for error diagnostics on an IHV
  profile.


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


## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>



<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>



 

 


