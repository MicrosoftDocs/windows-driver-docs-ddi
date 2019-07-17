---
UID: NE:wwan._WWAN_NETWORK_BLACKLIST_STATE
title: _WWAN_NETWORK_BLACKLIST_STATE (wwan.h)
description: The WWAN_NETWORK_BLACKLIST_STATE enumeration describes possible states of a modem's two different blacklists, the SIM provider blacklist and the network provider blacklist.
tech.root: netvista
ms.assetid: 5b07ce87-fbdb-495b-8a58-60141a34e52b
ms.date: 08/21/2018
ms.topic: enum
f1_keywords:
 - "wwan/_WWAN_NETWORK_BLACKLIST_STATE"
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
targetos: Windows
ms.custom: RS5
---

# _WWAN_NETWORK_BLACKLIST_STATE enumeration

## -description

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

[MB Network Blacklist Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-network-blacklist-operations)

[OID_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-network-blacklist.md)

[**WWAN_NETWORK_BLACKLIST_INFO**](ns-wwan-_wwan_network_blacklist_info.md)
