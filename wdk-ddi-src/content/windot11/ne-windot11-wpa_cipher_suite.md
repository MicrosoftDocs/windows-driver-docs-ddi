---
UID: NE:windot11.WPA_CIPHER_SUITE
tech.root: netvista
title: WPA_CIPHER_SUITE
ms.date: 02/05/2024
targetos: Windows
description: The WPA_CIPHER_SUITE enumeration defines the Wi-Fi Protected Access (WPA) cipher suites.
prerelease: 
req.construct-type: enumeration
req.ddi-compliance: 
req.header: windot11.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - WPA_CIPHER_SUITE
f1_keywords:
 - WPA_CIPHER_SUITE
 - windot11/WPA_CIPHER_SUITE
dev_langs:
 - c++
helpviewer_keywords:
 - WPA_CIPHER_SUITE
---

# WPA_CIPHER_SUITE enumeration (windot11.h)

## -description

The **WPA_CIPHER_SUITE** enumeration defines Wi-Fi Protected Access (WPA) cipher suites.

## -enum-fields

### -field wpa_cipher_none:CIPHER_FROM_TYPE(WPA_OUI_PREFIX, 0)

No cipher suite.

### -field wpa_cipher_wep40:CIPHER_FROM_TYPE(WPA_OUI_PREFIX, 1)

WEP-40 (Wired Equivalent Privacy).

### -field wpa_cipher_tkip:CIPHER_FROM_TYPE(WPA_OUI_PREFIX, 2)

TKIP (Temporal Key Integrity Protocol).

### -field wpa_cipher_ccmp_128:CIPHER_FROM_TYPE(WPA_OUI_PREFIX, 4)

CCMP-128 (Counter Mode Cipher Block Chaining Message Authentication Code Protocol).

### -field wpa_cipher_wep104:CIPHER_FROM_TYPE(WPA_OUI_PREFIX, 5)

WEP-104.

### -field wpa_cipher_bip_cmac_128:CIPHER_FROM_TYPE(WPA_OUI_PREFIX, 6)

BIP-CMAC-128 (Broadcast Integrity Protocol Cipher-based Message Authentication Code).

### -field wpa_cipher_max:wpa_cipher_bip_cmac_128

The maximum range of the **WPA_CIPHER_SUITE** enumeration.


## -remarks

## -see-also

[**RSNA_CIPHER_SUITE**](ne-windot11-rsna_cipher_suite.md)

[WiFiCx Wi-Fi 7 feature requirements](/windows-hardware/drivers/netcx/wificx-wi-fi-7)