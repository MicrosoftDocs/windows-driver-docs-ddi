---
UID: NE:wlantypes._DOT11_CIPHER_ALGORITHM
title: "_DOT11_CIPHER_ALGORITHM"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_algorithm.htm
old-project: netvista
ms.assetid: 5fc1af01-7dd5-43dd-aefe-99dec0b5aa6a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wlantypes/DOT11_CIPHER_ALGO_WEP, DOT11_CIPHER_ALGO_CCMP, DOT11_CIPHER_ALGO_WEP104, wlantypes/DOT11_CIPHER_ALGO_CCMP, wlantypes/DOT11_CIPHER_ALGO_RSN_USE_GROUP, DOT11_CIPHER_ALGORITHM, PDOT11_CIPHER_ALGORITHM enumeration pointer [Network Drivers Starting with Windows Vista], DOT11_CIPHER_ALGO_RSN_USE_GROUP, DOT11_CIPHER_ALGORITHM enumeration [Network Drivers Starting with Windows Vista], DOT11_CIPHER_ALGO_WEP, wlantypes/DOT11_CIPHER_ALGO_WEP40, netvista.dot11_cipher_algorithm, DOT11_CIPHER_ALGO_WEP40, wlantypes/DOT11_CIPHER_ALGO_IHV_START, Native_802.11_data_types_f6b802d4-cd15-49ca-9518-5dceb9c2b651.xml, wlantypes/DOT11_CIPHER_ALGO_TKIP, DOT11_CIPHER_ALGO_IHV_START, PDOT11_CIPHER_ALGORITHM, *PDOT11_CIPHER_ALGORITHM, wlantypes/DOT11_CIPHER_ALGO_WEP104, wlantypes/DOT11_CIPHER_ALGO_BIP, DOT11_CIPHER_ALGO_TKIP, wlantypes/DOT11_CIPHER_ALGORITHM, DOT11_CIPHER_ALGO_NONE, DOT11_CIPHER_ALGO_BIP, DOT11_CIPHER_ALGO_IHV_END, wlantypes/DOT11_CIPHER_ALGO_IHV_END, wlantypes/DOT11_CIPHER_ALGO_WPA_USE_GROUP, wlantypes/PDOT11_CIPHER_ALGORITHM, DOT11_CIPHER_ALGO_WPA_USE_GROUP, _DOT11_CIPHER_ALGORITHM, wlantypes/DOT11_CIPHER_ALGO_NONE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wlantypes.h
apiname:
-	DOT11_CIPHER_ALGORITHM
product: Windows
targetos: Windows
req.typenames: DOT11_CIPHER_ALGORITHM, *PDOT11_CIPHER_ALGORITHM
req.product: Windows 10 or later.
---

# _DOT11_CIPHER_ALGORITHM enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CIPHER_ALGORITHM enumeration defines a cipher algorithm for data encryption and
  decryption.


## -syntax


````
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
````


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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569366">OID_DOT11_EXTSTA_CAPABILITY</a>.

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
    <a href="https://msdn.microsoft.com/f07d2d77-ccaf-4599-b59e-6ea4ecf55e0f">Open System Authentication</a> or 
    <a href="https://msdn.microsoft.com/41dd280b-e54c-4233-8051-45e7b1284d1d">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569436">OID_DOT11_WPS_ENABLED</a>.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569135">OID_DOT11_CURRENT_PHY_ID</a>



<a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a>



<a href="..\windot11\ns-windot11-dot11_cipher_algorithm_list.md">DOT11_CIPHER_ALGORITHM_LIST</a>



<a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">DOT11_AUTH_CIPHER_PAIR_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CIPHER_ALGORITHM enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

