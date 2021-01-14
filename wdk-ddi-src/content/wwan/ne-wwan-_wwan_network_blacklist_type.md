---
UID: NE:wwan._WWAN_NETWORK_BLACKLIST_TYPE
title: _WWAN_NETWORK_BLACKLIST_TYPE (wwan.h)
description: The WWAN_NETWORK_BLACKLIST_TYPE enumeration specifies which of a mobile broadband (MBB) modem's two network blacklists is used for an MCC/MNC pair.
tech.root: netvista
ms.date: 08/21/2018
keywords: ["WWAN_NETWORK_BLACKLIST_TYPE enumeration"]
ms.keywords: _WWAN_NETWORK_BLACKLIST_TYPE, WWAN_NETWORK_BLACKLIST_TYPE,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WWAN_NETWORK_BLACKLIST_TYPE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_NETWORK_BLACKLIST_TYPE
 - wwan/_WWAN_NETWORK_BLACKLIST_TYPE
 - WWAN_NETWORK_BLACKLIST_TYPE
 - wwan/WWAN_NETWORK_BLACKLIST_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NETWORK_BLACKLIST_TYPE
 - WWAN_NETWORK_BLACKLIST_TYPE
product:
 - Windows
---

# _WWAN_NETWORK_BLACKLIST_TYPE enumeration


## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

The **WWAN_NETWORK_BLACKLIST_TYPE** enumeration specifies which of a mobile broadband (MBB) modem's two network blacklists is used for an MCC/MNC pair.

## -enum-fields

### -field WwanNetworkBlacklistTypeSIM 

The MCC/MNC pair is used for the SIM provider blacklist.

### -field WwanNetworkBlacklistTypeNetwork 

The MCC/MNC pair is used for the network provider blacklist.

### -field WwanNetworkBlacklistTypeMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_NETWORK_BLACKLIST_PROVIDER**](ns-wwan-_wwan_network_blacklist_provider.md) structure.

## -see-also

[MB Network Blacklist Operations](/windows-hardware/drivers/network/mb-network-blacklist-operations)

[**WWAN_NETWORK_BLACKLIST_PROVIDER**](ns-wwan-_wwan_network_blacklist_provider.md)

