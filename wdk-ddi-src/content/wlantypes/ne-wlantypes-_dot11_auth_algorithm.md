---
UID: NE:wlantypes._DOT11_AUTH_ALGORITHM
title: _DOT11_AUTH_ALGORITHM (wlantypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_auth_algorithm.htm
tech.root: netvista
ms.assetid: 27bba553-2d46-4892-864a-52e44caf6d56
ms.date: 02/16/2018
keywords: ["DOT11_AUTH_ALGORITHM enumeration"]
ms.keywords: "*PDOT11_AUTH_ALGORITHM, DOT11_AUTH_ALGORITHM, DOT11_AUTH_ALGORITHM enumeration [Network Drivers Starting with Windows Vista], DOT11_AUTH_ALGO_80211_OPEN, DOT11_AUTH_ALGO_80211_SHARED_KEY, DOT11_AUTH_ALGO_IHV_END, DOT11_AUTH_ALGO_IHV_START, DOT11_AUTH_ALGO_RSNA, DOT11_AUTH_ALGO_RSNA_PSK, DOT11_AUTH_ALGO_WPA, DOT11_AUTH_ALGO_WPA_NONE, DOT11_AUTH_ALGO_WPA_PSK, Native_802.11_data_types_e6d2770c-b7fd-467c-a94e-b2f77a515e76.xml, PDOT11_AUTH_ALGORITHM, PDOT11_AUTH_ALGORITHM enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_AUTH_ALGORITHM, netvista.dot11_auth_algorithm, wlantypes/DOT11_AUTH_ALGORITHM, wlantypes/DOT11_AUTH_ALGO_80211_OPEN, wlantypes/DOT11_AUTH_ALGO_80211_SHARED_KEY, wlantypes/DOT11_AUTH_ALGO_IHV_END, wlantypes/DOT11_AUTH_ALGO_IHV_START, wlantypes/DOT11_AUTH_ALGO_RSNA, wlantypes/DOT11_AUTH_ALGO_RSNA_PSK, wlantypes/DOT11_AUTH_ALGO_WPA, wlantypes/DOT11_AUTH_ALGO_WPA_NONE, wlantypes/DOT11_AUTH_ALGO_WPA_PSK, wlantypes/PDOT11_AUTH_ALGORITHM"
req.header: wlantypes.h
req.include-header: Ndis.h
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
req.typenames: DOT11_AUTH_ALGORITHM, *PDOT11_AUTH_ALGORITHM, DOT11_AUTH_ALGORITHM, *PDOT11_AUTH_ALGORITHM
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11_AUTH_ALGORITHM
 - wlantypes/_DOT11_AUTH_ALGORITHM
 - PDOT11_AUTH_ALGORITHM
 - wlantypes/PDOT11_AUTH_ALGORITHM
 - DOT11_AUTH_ALGORITHM
 - wlantypes/DOT11_AUTH_ALGORITHM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlantypes.h
api_name:
 - DOT11_AUTH_ALGORITHM
---

# _DOT11_AUTH_ALGORITHM enumeration


## -description

<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_AUTH_ALGORITHM enumeration defines a wireless LAN (WLAN) authentication algorithm.

## -enum-fields

### -field DOT11_AUTH_ALGO_80211_OPEN

      Specifies an IEEE 802.11 Open System authentication algorithm.

### -field DOT11_AUTH_ALGO_80211_SHARED_KEY

Specifies an IEEE 802.11 Shared Key authentication algorithm that requires the use of a pre-shared
     Wired Equivalent Privacy (WEP) key for the 802.11 authentication.

### -field DOT11_AUTH_ALGO_WPA

Specifies a Wi-Fi Protected Access (WPA) algorithm. IEEE 802.1X port authorization is performed by
     the supplicant, authenticator, and authentication server. Cipher keys are dynamically derived through
     the authentication process.


This algorithm is valid only for basic service set (BSS) types of
     dot11_BSS_type_infrastructure.

When the WPA algorithm is enabled, the 802.11 station associates only with an access point whose
     beacon or probe responses contain the authentication suite of type 1 (802.1X) within the WPA information
     element (IE).

### -field DOT11_AUTH_ALGO_WPA_PSK

Specifies a Wi-Fi Protected Access (WPA) algorithm that uses preshared keys (PSK). IEEE 802.1X
     port authorization is performed by the supplicant and authenticator. Cipher keys are dynamically derived
     through a preshared key that is used on both the supplicant and authenticator.


This algorithm is valid only for BSS types of
     dot11_BSS_type_infrastructure.

When the WPA PSK algorithm is enabled, the 802.11 station will associate only with an access point
     whose beacon or probe responses contain the authentication suite of type 2 (preshared key) within the
     WPA IE.

### -field DOT11_AUTH_ALGO_WPA_NONE

This value is not supported.

### -field DOT11_AUTH_ALGO_RSNA

Specifies an IEEE 802.11i Robust Security Network Association (RSNA) algorithm. IEEE 802.1X port
     authorization is performed by the supplicant, authenticator, and authentication server. Cipher keys are
     dynamically derived through the authentication process.


This algorithm is valid only for BSS types of
     dot11_BSS_type_infrastructure.

When the RSNA algorithm is enabled, the 802.11 station will associate only with an access point whose
     beacon or probe responses contain the authentication suite of type 1 (802.1X) within the Robust Security
     Network (RSN) IE.

### -field DOT11_AUTH_ALGO_RSNA_PSK

Specifies an IEEE 802.11i RSNA algorithm that uses PSK. IEEE 802.1X port authorization is
     performed by the supplicant and authenticator. Cipher keys are dynamically derived through a pre-shared
     key that is used on both the supplicant and authenticator.


When the RSNA PSK algorithm is enabled, the 802.11 station will associate only with an access point
     whose beacon or probe responses contain the authentication suite of type 2 (preshared key) within the
     RSN IE.

### -field DOT11_AUTH_ALGO_IHV_START

Specifies the start of the range that specifies proprietary authentication algorithms that are
     developed by an IHV.


The
     DOT11_AUTH_ALGO_IHV_START enumerator is valid only when the miniport driver is operating in
     Extensible Station (ExtSTA) mode.

### -field DOT11_AUTH_ALGO_IHV_END

Specifies the end of the range that specifies proprietary authentication algorithms that are
     developed by an IHV.


The
     DOT11_AUTH_ALGO_IHV_END enumerator is valid only when the miniport driver is operating in ExtSTA
     mode.

### -field v1_enum

## -syntax

```cpp
typedef enum _DOT11_AUTH_ALGORITHM {
  DOT11_AUTH_ALGO_80211_OPEN        = 1,
  DOT11_AUTH_ALGO_80211_SHARED_KEY  = 2,
  DOT11_AUTH_ALGO_WPA               = 3,
  DOT11_AUTH_ALGO_WPA_PSK           = 4,
  DOT11_AUTH_ALGO_WPA_NONE          = 5,
  DOT11_AUTH_ALGO_RSNA              = 6,
  DOT11_AUTH_ALGO_RSNA_PSK          = 7,
  DOT11_AUTH_ALGO_IHV_START         = 0x80000000,
  DOT11_AUTH_ALGO_IHV_END           = 0xffffffff
} DOT11_AUTH_ALGORITHM, *PDOT11_AUTH_ALGORITHM;
```

## -remarks

An IHV can assign a value for its proprietary authentication algorithms from
    DOT11_AUTH_ALGO_IHV_START through
    DOT11_AUTH_ALGO_IHV_END. The IHV must assign a unique number from this range for each of its
    proprietary authentication algorithms.

If the IHV develops its own support for an authentication algorithm supported by the operating system,
    the IHV must also assign a unique number from this range. For example, if the IHV develops its own
    version of RSNA, it must assign a value for this version from
    DOT11_AUTH_ALGO_IHV_START through
    DOT11_AUTH_ALGO_IHV_END.

<div class="alert"><b>Note</b>  The 802.11 station must implicitly enable the 802.11 Open System authentication
    algorithm whenever it enables a WPA or RSNA authentication algorithm.</div>
<div> </div>
Starting with Windows 7, an 802.11 miniport driver can report any combination of supported
    authentication and cipher algorithm pairs in the
    <a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">
    DOT11_AUTH_CIPHER_PAIR_LIST</a> structure. However, if the operating system starts Soft AP, it enables
    only the
    DOT11_AUTH_ALGO_RSNA_PSK authentication algorithm and the
    DOT11_CIPHER_ALGO_CCMP cipher algorithm. To support Soft AP, the miniport driver must support this
    authentication/cipher pair.

If WPS is enabled on a NIC that is operating in Extensible AP mode, the miniport driver must allow
    peer stations to associate with the Extensible AP by using
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/open-system-authentication">Open System Authentication</a> or
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565846(v=vs.85)">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wps-enabled">OID_DOT11_WPS_ENABLED</a>.

## -see-also

<a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a>



<a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">DOT11_AUTH_CIPHER_PAIR_LIST</a>



<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg159168(v=winembedded.80)">
   OID_DOT11_ENABLED_AUTHENTICATION_ALGORITHM</a>



<a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a>

