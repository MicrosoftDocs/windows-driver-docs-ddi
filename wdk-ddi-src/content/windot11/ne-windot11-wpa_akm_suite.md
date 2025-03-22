---
UID: NE:windot11.WPA_AKM_SUITE
tech.root: netvista
title: WPA_AKM_SUITE
ms.date: 02/05/2024
targetos: Windows
description: The WPA_AKM_SUITE enumeration defines WPA AKM suites.
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
 - WPA_AKM_SUITE
f1_keywords:
 - WPA_AKM_SUITE
 - windot11/WPA_AKM_SUITE
dev_langs:
 - c++
helpviewer_keywords:
 - WPA_AKM_SUITE
---

# WPA_AKM_SUITE enumeration (windot11.h)

## -description

The **WPA_AKM_SUITE** enumeration defines Wi-Fi Protected Access (WPA) authentication and key management (AKM) suites.

## -enum-fields

### -field wpa_akm_none:(WPA_OUI_PREFIX, 0)

No WPA AKM suite.

### -field wpa_akm_1x:(WPA_OUI_PREFIX, 1)

IEEE 802.1X authentication with a Pseudo-Random Function (PRF) of 128 bits.

### -field wpa_akm_psk:(WPA_OUI_PREFIX, 2)

Pre-Shared Key (PSK) authentication with a PRF of 128 bits.

### -field wpa_akm_max:wpa_akm_psk

The maximum range of the **WPA_AKM_SUITE** enum.

## -remarks

## -see-also

[**AKM_FROM_TYPE**](nf-windot11-akm_from_type.md)

[**RSNA_AKM_SUITE**](ne-windot11-rsna_akm_suite.md)

[WiFiCx Wi-Fi 7 feature requirements](/windows-hardware/drivers/netcx/wificx-wi-fi-7)

