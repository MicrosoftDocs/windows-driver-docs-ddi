---
UID: NS:windot11.RSNA_AKM_CIPHER_PAIR
tech.root: netvista
title: RSNA_AKM_CIPHER_PAIR
ms.date: 02/06/2024
targetos: Windows
description: The RSNA_AKM_CIPHER_PAIR structure defines a Robust Security Network Association (RSNA) authentication and key management (AKM) and cipher pair.
prerelease: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: windot11.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: RSNA_AKM_CIPHER_PAIR
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - RSNA_AKM_CIPHER_PAIR
f1_keywords:
 - RSNA_AKM_CIPHER_PAIR
 - windot11/RSNA_AKM_CIPHER_PAIR
dev_langs:
 - c++
helpviewer_keywords:
 - RSNA_AKM_CIPHER_PAIR
---

# RSNA_AKM_CIPHER_PAIR structure (windot11.h)

## -description

The **RSNA_AKM_CIPHER_PAIR** structure represents a Robust Security Network Association (RSNA) authentication and key management (AKM) and encryption cipher pair.

## -struct-fields

### -field akm

An [**RSNA_AKM_SUITE**](ne-windot11-rsna_akm_suite.md) enumeration value that specifies the RSNA AKM suite.

### -field cipher

An [**RSNA_CIPHER_SUITE**](ne-windot11-rsna_cipher_suite.md) enumeration value that specifies the RSNA cipher suite.

## -remarks

The **RSNA_AKM_CIPHER_PAIR** structure is used in the [WDI_TLV_RSNA_AKM_CIPHER_SUITE](/windows-hardware/drivers/netcx/wdi-tlv-rsna-akm-cipher-suite) TLV.

## -see-also

[**RSNA_AKM_SUITE**](ne-windot11-rsna_akm_suite.md)

[**RSNA_CIPHER_SUITE**](ne-windot11-rsna_cipher_suite.md)

[WDI_TLV_RSNA_AKM_CIPHER_SUITE](/windows-hardware/drivers/netcx/wdi-tlv-rsna-akm-cipher-suite)

[WiFiCx Wi-Fi 7 feature requirements](/windows-hardware/drivers/netcx/wificx-wi-fi-7)