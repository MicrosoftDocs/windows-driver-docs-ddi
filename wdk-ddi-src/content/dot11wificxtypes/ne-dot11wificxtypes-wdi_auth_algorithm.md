---
UID: NE:dot11wificxtypes._WDI_AUTH_ALGORITHM
tech.root: netvista
<<<<<<< HEAD
title: WDI_AUTH_ALGORITHM (dot11wificxtypes.h)
ms.date: 06/17/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_AUTH_ALGORITHM enumeration defines authentication algorithm values.
=======
title: WDI_AUTH_ALGORITHM
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_AUTH_ALGORITHM enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
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
 - _WDI_AUTH_ALGORITHM
 - WDI_AUTH_ALGORITHM
f1_keywords:
 - _WDI_AUTH_ALGORITHM
 - dot11wificxtypes/_WDI_AUTH_ALGORITHM
 - WDI_AUTH_ALGORITHM
 - dot11wificxtypes/WDI_AUTH_ALGORITHM
dev_langs:
 - c++
---

## -description

The **WDI_AUTH_ALGORITHM** enumeration defines the authentication algorithm values.

## -enum-fields

### -field WDI_AUTH_ALGO_80211_OPEN

Specifies an IEEE 802.11 Open System authentication algorithm.

### -field WDI_AUTH_ALGO_80211_SHARED_KEY

Specifies an IEEE 802.11 Shared Key authentication algorithm that requires the use of a pre-shared Wired Equivalent Privacy (WEP) key for the 802.11 authentication.

### -field WDI_AUTH_ALGO_WPA

Specifies a Wi-Fi Protected Access (WPA) algorithm. IEEE 802.1X port authorization is performed by the supplicant, authenticator, and authentication server. Cipher keys are dynamically derived through the authentication process. 

When the WPA algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 1 (802.1X) within the WPA information element (IE).

### -field WDI_AUTH_ALGO_WPA_PSK

Specifies a Wi-Fi Protected Access (WPA) algorithm that uses preshared keys (PSK). IEEE 802.1X port authorization is performed by the supplicant and authenticator. Cipher keys are dynamically derived through a preshared key that is used on both the supplicant and authenticator. 

When the WPA PSK algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 2 (preshared key) within the WPA IE.

### -field WDI_AUTH_ALGO_WPA_NONE

This value is not supported.

### -field WDI_AUTH_ALGO_RSNA

Specifies an IEEE 802.11i Robust Security Network Association (RSNA) algorithm. IEEE 802.1X port authorization is performed by the supplicant, authenticator, and authentication server. Cipher keys are dynamically derived through the authentication process. 

When the RSNA algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 1 (802.1X) within the Robust Security Network (RSN) IE.

### -field WDI_AUTH_ALGO_RSNA_PSK

Specifies an IEEE 802.11i RSNA algorithm that uses PSK. IEEE 802.1X port authorization is performed by the supplicant and authenticator. Cipher keys are dynamically derived through a pre-shared key that is used on both the supplicant and authenticator. 

When the RSNA PSK algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 2 (preshared key) within the RSN IE.

### -field WDI_AUTH_ALGO_WPA3_ENT_192

Specifies a WPA3-Enterprise 192-bit mode algorithm.

### -field WDI_AUTH_ALGO_WPA3_SAE

Specifies a WPA3-Simultaneous Authentication of Equals (WPA3-SAE) algorithm.

### -field WDI_AUTH_ALGO_OWE

Specifies an opportunistic wireless encryption (OWE) algorithm.

### -field WDI_AUTH_ALGO_WPA3_ENT

Specifies a WPA3-Enterprise algorithm.

### -field WDI_AUTH_ALGO_IHV_START

Specifies the start of the range that specifies proprietary authentication algorithms that are developed by an IHV.

### -field WDI_AUTH_ALGO_IHV_END

Specifies the end of the range that specifies proprietary authentication algorithms that are developed by an IHV.

## -remarks

## -see-also

[**WDI_TLV_UNICAST_ALGORITHM_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-unicast-algorithm-list)

[**WDI_TLV_AUTH_ALGO_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-auth-algo-list)

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters)

[**WDI_TLV_ASSOCIATION_RESPONSE_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-response-result-parameters)