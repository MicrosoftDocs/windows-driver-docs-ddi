---
UID: NE:wwan._WWAN_NETWORK_BLACKLIST_TYPE
title: _WWAN_NETWORK_BLACKLIST_TYPE (wwan.h)
description: The WWAN_NETWORK_BLACKLIST_TYPE enumeration specifies which of a mobile broadband (MBB) modem's two network blacklists is used for an MCC/MNC pair.
tech.root: netvista
ms.assetid: 65355b7a-b564-40bf-8f8c-fa75d32ec8cb
ms.date: 08/21/2018
ms.topic: enum
f1_keywords:
 - "wwan/_WWAN_NETWORK_BLACKLIST_TYPE"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_NETWORK_BLACKLIST_TYPE
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_NETWORK_BLACKLIST_TYPE enumeration

## -description

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

[MB Network Blacklist Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-network-blacklist-operations)

[**WWAN_NETWORK_BLACKLIST_PROVIDER**](ns-wwan-_wwan_network_blacklist_provider.md)
