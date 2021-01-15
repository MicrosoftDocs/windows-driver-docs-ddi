---
UID: NS:windot11.DOT11_KEY_ALGO_CCMP
title: DOT11_KEY_ALGO_CCMP (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_key_algo_ccmp.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_KEY_ALGO_CCMP structure"]
ms.keywords: "*PDOT11_KEY_ALGO_CCMP, DOT11_KEY_ALGO_CCMP, DOT11_KEY_ALGO_CCMP structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_37999ce3-5aae-4c91-80f0-f47a7182a963.xml, PDOT11_KEY_ALGO_CCMP, PDOT11_KEY_ALGO_CCMP structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_key_algo_ccmp, windot11/DOT11_KEY_ALGO_CCMP, windot11/PDOT11_KEY_ALGO_CCMP"
req.header: windot11.h
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
req.typenames: DOT11_KEY_ALGO_CCMP, *PDOT11_KEY_ALGO_CCMP
f1_keywords:
 - DOT11_KEY_ALGO_CCMP
 - windot11/DOT11_KEY_ALGO_CCMP
 - PDOT11_KEY_ALGO_CCMP
 - windot11/PDOT11_KEY_ALGO_CCMP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_KEY_ALGO_CCMP
 - PDOT11_KEY_ALGO_CCMP
product:
 - Windows 10 or later.
---

# DOT11_KEY_ALGO_CCMP structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_KEY_ALGO_CCMP structure defines a cipher key that is used by the AES-CCMP algorithm for
  data encryption and decryption.

## -struct-fields

### -field ucIV48Counter

The initial 48-bit value of the AES-CCMP Packet Number (PN), which is used for replay protection.
     For more information about the PN, see
     <a href="/windows-hardware/drivers/network/aes-ccmp">AES-CCMP</a>.

### -field ulCCMPKeyLength

The length, in bytes, of the AES-CCMP key material in the
     <b>ucCCMPKey</b> array. If the authentication and cipher key derivation is performed by the operating
     system, this member will always have a value of 16.

### -field ucCCMPKey

The AES-CCMP key material.

## -syntax

```cpp
typedef struct DOT11_KEY_ALGO_CCMP {
  UCHAR ucIV48Counter[6];
  ULONG ulCCMPKeyLength;
  UCHAR ucCCMPKey[1];
} DOT11_KEY_ALGO_CCMP, *PDOT11_KEY_ALGO_CCMP;
```

## -remarks

When the AES-CCMP key is created, the 802.11 station must maintain separate PN counters for the key
    for the send and receive path. The station must initialize the PN counters in the following way:

<ul>
<li>
Initialize the PN counter used for the receive path to the value specified in the
      <b>ucIV48Counter</b> member.

</li>
<li>
Initialize the PN counter used for the send path to any value.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="/windows-hardware/drivers/network/aes-ccmp">AES-CCMP</a>



<a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
   DOT11_CIPHER_DEFAULT_KEY_VALUE</a>

