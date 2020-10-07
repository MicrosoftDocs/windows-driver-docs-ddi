---
UID: NE:wwan._WWAN_NETWORK_BLACKLIST_STATE
title: _WWAN_NETWORK_BLACKLIST_STATE (wwan.h)
description: The WWAN_NETWORK_BLACKLIST_STATE enumeration describes possible states of a modem's two different blacklists, the SIM provider blacklist and the network provider blacklist.
tech.root: netvista
ms.assetid: 5b07ce87-fbdb-495b-8a58-60141a34e52b
ms.date: 08/21/2018
keywords: ["WWAN_NETWORK_BLACKLIST_STATE enumeration"]
ms.keywords: _WWAN_NETWORK_BLACKLIST_STATE, WWAN_NETWORK_BLACKLIST_STATE,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WWAN_NETWORK_BLACKLIST_STATE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_NETWORK_BLACKLIST_STATE
 - wwan/_WWAN_NETWORK_BLACKLIST_STATE
 - WWAN_NETWORK_BLACKLIST_STATE
 - wwan/WWAN_NETWORK_BLACKLIST_STATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NETWORK_BLACKLIST_STATE
product:
 - Windows
---

# _WWAN_NETWORK_BLACKLIST_STATE enumeration


## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

The **WWAN_NETWORK_BLACKLIST_STATE** enumeration describes possible states of a modem's two different blacklists, the SIM provider blacklist and the network provider blacklist.

## -enum-fields

### -field WwanNetworkBlacklistStateNotActuated 

Both blacklist conditions are not met.

### -field WwanNetworkBlacklistSIMProviderActuated 

The inserted SIM is blacklisted because its provider ID matches the blacklist for SIM provider IDs.

### -field WwanNetworkBlacklistNetworkProviderActuated 

Available networks are blacklisted because their provider IDs are all in the blacklist for network provider IDs.

### -field WwanNetworkBlacklistStateMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_NETWORK_BLACKLIST_INFO**](ns-wwan-_wwan_network_blacklist_info.md) structure.

## -see-also

[MB Network Blacklist Operations](/windows-hardware/drivers/network/mb-network-blacklist-operations)

[**WWAN_NETWORK_BLACKLIST_INFO**](ns-wwan-_wwan_network_blacklist_info.md)