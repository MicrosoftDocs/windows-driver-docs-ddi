---
UID: NE:windot11.RSNA_CIPHER_SUITE
tech.root: netvista
title: RSNA_CIPHER_SUITE
ms.date: 02/05/2024
targetos: Windows
description: The RSNA_CIPHER_SUITE enumeration specifies the Robust Security Network Association (RSNA) cipher suites.
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
 - RSNA_CIPHER_SUITE
f1_keywords:
 - RSNA_CIPHER_SUITE
 - windot11/RSNA_CIPHER_SUITE
dev_langs:
 - c++
helpviewer_keywords:
 - RSNA_CIPHER_SUITE
---

# RSNA_CIPHER_SUITE enumeration (windot11.h)

## -description

The **RSNA_CIPHER_SUITE** enumeration defines Robust Security Network Association (RSNA) cipher suites.

## -enum-fields

### -field rsna_cipher_group:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 0)

The default group cipher suite for the RSNA protocol.

### -field rsna_cipher_wep40:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 1)

WEP-40 (Wired Equivalent Privacy).

### -field rsna_cipher_tkip:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 2)

TKIP (Temporal Key Integrity Protocol).

### -field rsna_cipher_reserved:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 3)

Reserved.

### -field rsna_cipher_ccmp_128:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 4)

CCMP-128 (Counter Mode Cipher Block Chaining Message Authentication Code Protocol).

### -field rsna_cipher_wep104:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 5)

WEP-104.

### -field rsna_cipher_bip_cmac_128:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 6)

BIP-CMAC-128 (Broadcast Integrity Protocol Cipher-based Message Authentication Code).

### -field rsna_cipher_no_group_traffic:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 7)

No group traffic is allowed.

### -field rsna_cipher_gcmp_128:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 8)

GCMP-128 (Galois/Counter Mode Protocol).

### -field rsna_cipher_gcmp_256:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 9)

GCMP-256.

### -field rsna_cipher_ccmp_256:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 10)

CCMP-256.

### -field rsna_cipher_bip_gmac_128:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 11)

BIP-GMAC-128 (Broadcast Integrity Protocol Galois Message Authentication Code).

### -field rsna_cipher_bip_gmac_256:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 12)

BIP-GMAC-256.

### -field rsna_cipher_bip_cmac_256:CIPHER_FROM_TYPE(RSNA_OUI_PREFIX, 13)

BIP-CMAC-256.

### -field rsna_cipher_max:rsna_cipher_bip_cmac_256

The maximum range of the **RSNA_CIPHER_SUITE** enum.


## -remarks

## -see-also

[**RSNA_AKM_CIPHER_PAIR**](ns-windot11-rsna_akm_cipher_pair.md)

[WiFiCx Wi-Fi 7 feature requirements](/windows-hardware/drivers/netcx/wificx-wi-fi-7)