---
UID: NS:wlantypes.DOT11_AUTH_CIPHER_PAIR
title: DOT11_AUTH_CIPHER_PAIR (wlantypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_auth_cipher_pair.htm
tech.root: netvista
ms.assetid: 301e9c21-69e7-48d3-b170-de01684f4a12
ms.date: 02/16/2018
keywords: ["DOT11_AUTH_CIPHER_PAIR structure"]
ms.keywords: "*PDOT11_AUTH_CIPHER_PAIR, DOT11_AUTH_CIPHER_PAIR, DOT11_AUTH_CIPHER_PAIR structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_84940691-1e26-4039-927d-e1f1e0d14ea1.xml, PDOT11_AUTH_CIPHER_PAIR, PDOT11_AUTH_CIPHER_PAIR structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_auth_cipher_pair, wlantypes/DOT11_AUTH_CIPHER_PAIR, wlantypes/PDOT11_AUTH_CIPHER_PAIR"
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
req.typenames: DOT11_AUTH_CIPHER_PAIR, *PDOT11_AUTH_CIPHER_PAIR
req.product: Windows 10 or later.
f1_keywords:
 - DOT11_AUTH_CIPHER_PAIR
 - wlantypes/DOT11_AUTH_CIPHER_PAIR
 - PDOT11_AUTH_CIPHER_PAIR
 - wlantypes/PDOT11_AUTH_CIPHER_PAIR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlantypes.h
api_name:
 - DOT11_AUTH_CIPHER_PAIR
---

# DOT11_AUTH_CIPHER_PAIR structure


## -description

<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_AUTH_CIPHER_PAIR structure defines a pair of 802.11 authentication and cipher algorithms
  that can be enabled at the same time on the 802.11 station.

## -struct-fields

### -field AuthAlgoId

An authentication algorithm as specified by a
     <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a> value.

### -field CipherAlgoId

A cipher algorithm as specified by a
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> value.

## -syntax

```cpp
typedef struct DOT11_AUTH_CIPHER_PAIR {
  DOT11_AUTH_ALGORITHM   AuthAlgoId;
  DOT11_CIPHER_ALGORITHM CipherAlgoId;
} DOT11_AUTH_CIPHER_PAIR, *PDOT11_AUTH_CIPHER_PAIR;
```

## -remarks

The DOT11_AUTH_CIPHER_PAIR structure defines an authentication and cipher algorithm that can be
    enabled together for basic service set (BSS) network connections.

A miniport driver returns a list of these structures when either
    <a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg157261(v=winembedded.80)">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a> is queried.

Starting with Windows 7, an 802.11 miniport driver can report any combination of supported
    authentication and cipher algorithm pairs in the
    <a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">
    DOT11_AUTH_CIPHER_PAIR_LIST</a> structure. However, if the operating system starts Soft AP, it enables
    only the
    <b>DOT11_AUTH_ALGO_RSNA_PSK</b> authentication algorithm and the
    <b>DOT11_CIPHER_ALGO_CCMP</b> cipher algorithm. To support Soft AP, the miniport driver must support this
    authentication/cipher pair.<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="https://docs.microsoft.com/windows-hardware/drivers/partnerapps/wi-fi-direct">Wi-Fi Direct</a>.</div>
<div> </div>


If WPS is enabled on a NIC that is operating in Extensible AP mode, the miniport driver must allow
    peer stations to associate with the Extensible AP by using
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/open-system-authentication">Open System Authentication</a> or
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565846(v=vs.85)">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wps-enabled">OID_DOT11_WPS_ENABLED</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>



<a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">DOT11_AUTH_CIPHER_PAIR_LIST</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg157261(v=winembedded.80)">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>

