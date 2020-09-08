---
UID: NS:wwan._WWAN_NETWORK_BLACKLIST_PROVIDER
title: _WWAN_NETWORK_BLACKLIST_PROVIDER (wwan.h)
description: The WWAN_NETWORK_BLACKLIST_PROVIDER structure represents a network blacklist provider in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: ee770094-bb4c-44eb-a232-2de76de9ef6e
ms.date: 08/21/2018
keywords: ["WWAN_NETWORK_BLACKLIST_PROVIDER structure"]
ms.keywords: _WWAN_NETWORK_BLACKLIST_PROVIDER, WWAN_NETWORK_BLACKLIST_PROVIDER, *PWWAN_NETWORK_BLACKLIST_PROVIDER,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WWAN_NETWORK_BLACKLIST_PROVIDER, *PWWAN_NETWORK_BLACKLIST_PROVIDER
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_NETWORK_BLACKLIST_PROVIDER
 - wwan/_WWAN_NETWORK_BLACKLIST_PROVIDER
 - PWWAN_NETWORK_BLACKLIST_PROVIDER
 - wwan/PWWAN_NETWORK_BLACKLIST_PROVIDER
 - WWAN_NETWORK_BLACKLIST_PROVIDER
 - wwan/WWAN_NETWORK_BLACKLIST_PROVIDER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NETWORK_BLACKLIST_PROVIDER
product:
 - Windows
---

# _WWAN_NETWORK_BLACKLIST_PROVIDER structure


## -description

The **WWAN_NETWORK_BLACKLIST_PROVIDER** structure represents a network blacklist provider in a mobile broadband (MBB) modem.

## -struct-fields

### -field MCC

As specified by 3GPP, MCC is part of IMSI and specifies the country of the provider.

### -field MNC

As specified by 3GPP, MNC is part of IMSI and specifies the network of the provider.

### -field NetworkBlacklistType

A [**WWAN_NETWORK_BLACKLIST_TYPE**](ne-wwan-_wwan_network_blacklist_type.md) value that specifies for which type of blacklist the MCC/MNC pair is used.

## -remarks

A list of **WWAN_NETWORK_BLACKLIST_PROVIDER** structures follows the **BlacklistProviderList** member of the [**WWAN_NETWORK_BLACKLIST_INFO**](ns-wwan-_wwan_network_blacklist_info.md) structure.

## -see-also

[MB Network Blacklist Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-network-blacklist-operations)

[**WWAN_NETWORK_BLACKLIST_INFO**](ns-wwan-_wwan_network_blacklist_info.md)

[**WWAN_NETWORK_BLACKLIST_TYPE**](ne-wwan-_wwan_network_blacklist_type.md)

