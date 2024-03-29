---
UID: NE:dot11wificxtypes._WDI_CIPHER_ALGORITHM
tech.root: netvista
title: WDI_CIPHER_ALGORITHM (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CIPHER_ALGORITHM enum defines the cipher algorithm values.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_CIPHER_ALGORITHM
 - WDI_CIPHER_ALGORITHM
f1_keywords:
 - _WDI_CIPHER_ALGORITHM
 - dot11wificxtypes/_WDI_CIPHER_ALGORITHM
 - WDI_CIPHER_ALGORITHM
 - dot11wificxtypes/WDI_CIPHER_ALGORITHM
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The WDI_CIPHER_ALGORITHM enumeration defines the cipher algorithm values.

## -enum-fields

### -field WDI_CIPHER_ALGO_NONE:0x00

Specifies that no cipher algorithm is enabled or supported.

### -field WDI_CIPHER_ALGO_WEP40:0x01

Specifies a Wired Equivalent Privacy (WEP) algorithm, which is the RC4-based algorithm that is specified in the IEEE 802.11-2012 standard. This enumerator specifies the WEP cipher algorithm with a 40-bit cipher key.

### -field WDI_CIPHER_ALGO_TKIP:0x02

Specifies a Temporal Key Integrity Protocol (TKIP) algorithm, which is the RC4-based cipher suite that is based on the algorithms that are defined in the WPA specification and IEEE 802.11i-2004 standard. This cipher also uses the Michael Message Integrity Code (MIC) algorithm for forgery protection.

### -field WDI_CIPHER_ALGO_CCMP:0x04

Specifies an AES-CCMP algorithm, as specified in the IEEE 802.11i-2004 standard and RFC 3610. Advanced Encryption Standard (AES) is the encryption algorithm defined in FIPS PUB 197.

### -field WDI_CIPHER_ALGO_WEP104:0x05

Specifies a WEP cipher algorithm with a 104-bit cipher key.

### -field WDI_CIPHER_ALGO_BIP:0x06

Specifies a BIP cipher algorithm.

### -field WDI_CIPHER_ALGO_GCMP:0x08

Added in Windows 10, version 1607, WDI version 1.0.21.

Specifies a Galois/Counter Mode Protocol (GCMP) cipher algorithm. It is the only encryption protocol supported for 802.11ad (DMG) Phy.

### -field WDI_CIPHER_ALGO_GCMP_256:0x09

Added in Windows 10, version 2004, WDI version 1.1.9.

Specifies a GCMP cipher algorithm with a 256-bit cipher key.

### -field WDI_CIPHER_ALGO_CCMP_256:0x0a

Added in Windows 10, version 2004, WDI version 1.1.9.

Specifies an AES-CCMP algorithm with a 256-bit cipher key.

### -field WDI_CIPHER_ALGO_BIP_GMAC_128:0x0b

Added in Windows 10, version 2004, WDI version 1.1.9.

Specifies a Broadcast Integrity Protocol Galois Message Authentication Code (BIP-GMAC) cipher algorithm with a 128-bit cipher key.

### -field WDI_CIPHER_ALGO_BIP_GMAC_256:0x0c

Added in Windows 10, version 2004, WDI version 1.1.9.

Specifies a BIP-GMAC cipher algorithm with a 256-bit cipher key.

### -field WDI_CIPHER_ALGO_BIP_CMAC_256:0x0d

Added in Windows 10, version 2004, WDI version 1.1.9.

Specifies a Broadcast Integrity Protocol Cipher-based Message Authentication Code (BIP-CMAC) cipher algorithm with a 256-bit cipher key.

### -field WDI_CIPHER_ALGO_WPA_USE_GROUP:0x100

Specifies a Wi-Fi Protected Access (WPA) Use Group Key cipher suite. For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE 802.11i-2004 standard.

### -field WDI_CIPHER_ALGO_RSN_USE_GROUP:0x100

Specifies a Robust Security Network (RSN) Use Group Key cipher suite. For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE 802.11i-2004 standard.

### -field WDI_CIPHER_ALGO_WEP:0x101

Specifies a WEP cipher algorithm with a cipher key of any length.

### -field WDI_CIPHER_ALGO_IHV_START:0x80000000

Specifies the start of the range that is used to define proprietary cipher algorithms that are developed by an independent hardware vendor (IHV).

### -field WDI_CIPHER_ALGO_IHV_END:0xffffffff

Specifies the end of the range that is used to define proprietary authentication algorithms that are developed by an IHV.

## -remarks


## -see-also

[**WDI_TLV_UNICAST_ALGORITHM_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-unicast-algorithm-list)

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters)

[**WDI_TLV_MULTICAST_CIPHER_ALGO_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-multicast-cipher-algo-list)

[**WDI_TLV_ASSOCIATION_RESPONSE_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-response-result-parameters)
