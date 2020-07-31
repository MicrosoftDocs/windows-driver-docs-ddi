---
UID: NE:wlantypes._DOT11_CIPHER_ALGORITHM
title: _DOT11_CIPHER_ALGORITHM (wlantypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_algorithm.htm
tech.root: netvista
ms.assetid: 5fc1af01-7dd5-43dd-aefe-99dec0b5aa6a
ms.date: 02/16/2018
keywords: ["_DOT11_CIPHER_ALGORITHM enumeration"]
ms.keywords: "*PDOT11_CIPHER_ALGORITHM, DOT11_CIPHER_ALGORITHM, DOT11_CIPHER_ALGORITHM enumeration [Network Drivers Starting with Windows Vista], DOT11_CIPHER_ALGO_BIP, DOT11_CIPHER_ALGO_CCMP, DOT11_CIPHER_ALGO_IHV_END, DOT11_CIPHER_ALGO_IHV_START, DOT11_CIPHER_ALGO_NONE, DOT11_CIPHER_ALGO_RSN_USE_GROUP, DOT11_CIPHER_ALGO_TKIP, DOT11_CIPHER_ALGO_WEP, DOT11_CIPHER_ALGO_WEP104, DOT11_CIPHER_ALGO_WEP40, DOT11_CIPHER_ALGO_WPA_USE_GROUP, Native_802.11_data_types_f6b802d4-cd15-49ca-9518-5dceb9c2b651.xml, PDOT11_CIPHER_ALGORITHM, PDOT11_CIPHER_ALGORITHM enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_CIPHER_ALGORITHM, netvista.dot11_cipher_algorithm, wlantypes/DOT11_CIPHER_ALGORITHM, wlantypes/DOT11_CIPHER_ALGO_BIP, wlantypes/DOT11_CIPHER_ALGO_CCMP, wlantypes/DOT11_CIPHER_ALGO_IHV_END, wlantypes/DOT11_CIPHER_ALGO_IHV_START, wlantypes/DOT11_CIPHER_ALGO_NONE, wlantypes/DOT11_CIPHER_ALGO_RSN_USE_GROUP, wlantypes/DOT11_CIPHER_ALGO_TKIP, wlantypes/DOT11_CIPHER_ALGO_WEP, wlantypes/DOT11_CIPHER_ALGO_WEP104, wlantypes/DOT11_CIPHER_ALGO_WEP40, wlantypes/DOT11_CIPHER_ALGO_WPA_USE_GROUP, wlantypes/PDOT11_CIPHER_ALGORITHM"
f1_keywords:
 - "wlantypes/DOT11_CIPHER_ALGORITHM"
 - "DOT11_CIPHER_ALGORITHM"
req.header: wlantypes.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of the Windows operating   systems.
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
- wlantypes.h
api_name:
- DOT11_CIPHER_ALGORITHM
targetos: Windows
req.typenames: DOT11_CIPHER_ALGORITHM, *PDOT11_CIPHER_ALGORITHM, DOT11_CIPHER_ALGORITHM, *PDOT11_CIPHER_ALGORITHM
req.product: Windows 10 or later.
---

# _DOT11_CIPHER_ALGORITHM enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CIPHER_ALGORITHM enumeration defines a cipher algorithm for data encryption and
  decryption.


## -syntax


```cpp
typedef enum _DOT11_CIPHER_ALGORITHM {
  DOT11_CIPHER_ALGO_NONE           = 0x00,
  DOT11_CIPHER_ALGO_WEP40          = 0x01,
  DOT11_CIPHER_ALGO_TKIP           = 0x02,
  DOT11_CIPHER_ALGO_CCMP           = 0x04,
  DOT11_CIPHER_ALGO_WEP104         = 0x05,
  DOT11_CIPHER_ALGO_BIP            = 0x06,
  DOT11_CIPHER_ALGO_WPA_USE_GROUP  = 0x100,
  DOT11_CIPHER_ALGO_RSN_USE_GROUP  = 0x100,
  DOT11_CIPHER_ALGO_WEP            = 0x101,
  DOT11_CIPHER_ALGO_IHV_START      = 0x80000000,
  DOT11_CIPHER_ALGO_IHV_END        = 0xffffffff
} DOT11_CIPHER_ALGORITHM, *PDOT11_CIPHER_ALGORITHM;
```


## -enum-fields




### -field DOT11_CIPHER_ALGO_NONE

Specifies that no cipher algorithm is enabled or supported.


### -field DOT11_CIPHER_ALGO_WEP40

Specifies a Wired Equivalent Privacy (WEP) algorithm, which is the RC4-based algorithm that is
     specified in the IEEE 802.11-2012 standard. This enumerator specifies the WEP cipher algorithm with a
     40-bit cipher key.


### -field DOT11_CIPHER_ALGO_TKIP

Specifies a Temporal Key Integrity Protocol (TKIP) algorithm, which is the RC4-based cipher suite
     that is based on the algorithms that are defined in the WPA specification and IEEE 802.11i-2004
     standard. This cipher also uses the Michael Message Integrity Code (MIC) algorithm for forgery
     protection.


### -field DOT11_CIPHER_ALGO_CCMP

Specifies an AES-CCMP algorithm, as specified in the IEEE 802.11i-2004 standard and RFC 3610.
     Advanced Encryption Standard (AES) is the encryption algorithm defined in FIPS PUB 197.


### -field DOT11_CIPHER_ALGO_WEP104

Specifies a WEP cipher algorithm with a 104-bit cipher key.


### -field DOT11_CIPHER_ALGO_BIP

Specifies a BIP cipher algorithm.


### -field DOT11_CIPHER_ALGO_GCMP


### -field DOT11_CIPHER_ALGO_WPA_USE_GROUP

Specifies a Wifi Protected Access (WPA) Use Group Key cipher suite.

For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE
      802.11i-2004 standard.


### -field DOT11_CIPHER_ALGO_RSN_USE_GROUP

Specifies a Robust Security Network (RSN) Use Group Key cipher suite.

For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE
      802.11i-2004 standard.


### -field DOT11_CIPHER_ALGO_WEP

Specifies a WEP cipher algorithm with a cipher key of any length.


A miniport driver that operates in Extensible Station (ExtSTA) mode specifies the maximum WEP cipher
     key length through a query of
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-extsta-capability">OID_DOT11_EXTSTA_CAPABILITY</a>.

<div class="alert"><b>Note</b>  The operating system will only enable this cipher algorithm if authentication
     algorithms of
     <b>DOT11_AUTH_ALGO_80211_OPEN</b> or
     <b>DOT11_AUTH_ALGO_80211_SHARED_KEY</b> have been enabled. For more information about these
     authentication algorithms, see
     <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>.</div>
<div> </div>

### -field DOT11_CIPHER_ALGO_IHV_START

Specifies the start of the range that is used to define proprietary cipher algorithms that are
     developed by an independent hardware vendor (IHV).


The
     <b>DOT11_CIPHER_ALGO_IHV_START</b> enumerator is valid only when the miniport driver is operating in
     ExtSTA mode.


### -field DOT11_CIPHER_ALGO_IHV_END

Specifies the end of the range that is used to define proprietary authentication algorithms that
     are developed by an IHV.


The
     <b>DOT11_CIPHER_ALGO_IHV_END</b> enumerator is valid only when the miniport driver is operating in ExtSTA
     mode.


### -field v1_enum




## -remarks



An IHV can assign a value for its proprietary cipher algorithms from
    <b>DOT11_CIPHER_ALGO_IHV_START</b> through
    <b>DOT11_CIPHER_ALGO_IHV_END</b>. The IHV must assign a unique number in this range to each of its
    proprietary cipher algorithms.

If the IHV develops its own support for an cipher algorithm supported by the operating system, the IHV
    must also assign a unique number from this range. For example, if the IHV develops its own version of
    TKIP, it must assign a value for this version from
    <b>DOT11_CIPHER_ALGO_IHV_START</b> through
    <b>DOT11_CIPHER_ALGO_IHV_END</b>.

A miniport driver must enable or select cipher algorithms based on the following preference order
    (listed from highest to lowest):

<b>DOT11_CIPHER_ALGO_CCMP</b>

<b>DOT11_CIPHER_ALGO_TKIP</b>

<b>DOT11_CIPHER_ALGO_WEP</b>

<b>DOT11_CIPHER_ALGO_WEP104</b>

<b>DOT11_CIPHER_ALGO_WEP40</b>

<b>DOT11_CIPHER_ALGO_NONE</b>

If the miniport driver supports IHV-defined cipher algorithms, the miniport driver can determine the
    preference order for these algorithms with respect to the 802.11 standard cipher algorithms.

Starting with Windows 7, an 802.11 miniport driver can report any combination of supported
    authentication and cipher algorithm pairs in the
    <a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">
    DOT11_AUTH_CIPHER_PAIR_LIST</a> structure. However, if the operating system starts Soft AP, it enables
    only the
    <b>DOT11_AUTH_ALGO_RSNA_PSK</b> authentication algorithm and the
    <b>DOT11_CIPHER_ALGO_CCMP</b> cipher algorithm. To support Soft AP, the miniport driver must support this
    authentication/cipher pair.

If WPS is enabled on a NIC that is operating in Extensible AP mode, the miniport driver must allow
    peer stations to associate with the Extensible AP by using
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/open-system-authentication">Open System Authentication</a> or
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565846(v=vs.85)">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wps-enabled">OID_DOT11_WPS_ENABLED</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a>



<a href="..\windot11\ns-windot11-dot11_cipher_algorithm_list.md">DOT11_CIPHER_ALGORITHM_LIST</a>



<a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">DOT11_AUTH_CIPHER_PAIR_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-current-phy-id">OID_DOT11_CURRENT_PHY_ID</a>



 

 


