---
UID: NE:wditypes._WDI_AUTH_ALGORITHM
title: _WDI_AUTH_ALGORITHM (wditypes.h)
description: The WDI_AUTH_ALGORITHM enumeration defines the authentication algorithm values.
old-location: netvista\wdi_auth_algorithm.htm
tech.root: netvista
ms.assetid: B908A174-F977-484E-A086-6C8C9A914D6C
ms.date: 02/14/2019
keywords: ["WDI_AUTH_ALGORITHM enumeration"]
ms.keywords: WDI_AUTH_ALGORITHM, WDI_AUTH_ALGORITHM enumeration [Device and Driver Installation], WDI_AUTH_ALGO_80211_OPEN, WDI_AUTH_ALGO_80211_SHARED_KEY, WDI_AUTH_ALGO_IHV_END, WDI_AUTH_ALGO_IHV_START, WDI_AUTH_ALGO_RSNA, WDI_AUTH_ALGO_RSNA_PSK, WDI_AUTH_ALGO_WPA, WDI_AUTH_ALGO_WPA_NONE, WDI_AUTH_ALGO_WPA_PSK, _WDI_AUTH_ALGORITHM, netvista.wdi_auth_algorithm, netvista.wifi_auth_algorithm, wditypes/WDI_AUTH_ALGORITHM, wditypes/WDI_AUTH_ALGO_80211_OPEN, wditypes/WDI_AUTH_ALGO_80211_SHARED_KEY, wditypes/WDI_AUTH_ALGO_IHV_END, wditypes/WDI_AUTH_ALGO_IHV_START, wditypes/WDI_AUTH_ALGO_RSNA, wditypes/WDI_AUTH_ALGO_RSNA_PSK, wditypes/WDI_AUTH_ALGO_WPA, wditypes/WDI_AUTH_ALGO_WPA_NONE, wditypes/WDI_AUTH_ALGO_WPA_PSK
f1_keywords:
 - "wditypes/WDI_AUTH_ALGORITHM"
 - "WDI_AUTH_ALGORITHM"
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- wditypes.hpp
api_name:
- WDI_AUTH_ALGORITHM
targetos: Windows
req.typenames: WDI_AUTH_ALGORITHM
---

# _WDI_AUTH_ALGORITHM enumeration


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

### -field WDI_AUTH_ALGO_WPA3

Specifies a Wi-Fi Protected Access 3 (WPA3) algorithm.

### -field WDI_AUTH_ALGO_WPA3_SAE

Specifies a WPA3-Simultaneous Authentication of Equals (WPA3-SAE) algorithm.

### -field WDI_AUTH_ALGO_IHV_START

Specifies the start of the range that specifies proprietary authentication algorithms that are developed by an IHV. 

### -field WDI_AUTH_ALGO_IHV_END

Specifies the end of the range that specifies proprietary authentication algorithms that are developed by an IHV. 
