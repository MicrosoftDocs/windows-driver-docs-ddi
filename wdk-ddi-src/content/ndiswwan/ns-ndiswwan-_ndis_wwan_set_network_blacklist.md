---
UID: NS:ndiswwan._NDIS_WWAN_SET_NETWORK_BLACKLIST
title: _NDIS_WWAN_SET_NETWORK_BLACKLIST (ndiswwan.h)
description: The NDIS_WWAN_SET_NETWORK_BLACKLIST structure describes network blacklists that a mobile broadband (MBB) device should use to overwrite any existing blacklists in the modem.
tech.root: netvista
ms.date: 08/21/2018
keywords: ["NDIS_WWAN_SET_NETWORK_BLACKLIST structure"]
ms.keywords: _NDIS_WWAN_SET_NETWORK_BLACKLIST, NDIS_WWAN_SET_NETWORK_BLACKLIST, *PNDIS_WWAN_SET_NETWORK_BLACKLIST,
req.header: ndiswwan.h
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
req.typenames: NDIS_WWAN_SET_NETWORK_BLACKLIST, *PNDIS_WWAN_SET_NETWORK_BLACKLIST
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_WWAN_SET_NETWORK_BLACKLIST
 - ndiswwan/_NDIS_WWAN_SET_NETWORK_BLACKLIST
 - PNDIS_WWAN_SET_NETWORK_BLACKLIST
 - ndiswwan/PNDIS_WWAN_SET_NETWORK_BLACKLIST
 - NDIS_WWAN_SET_NETWORK_BLACKLIST
 - ndiswwan/NDIS_WWAN_SET_NETWORK_BLACKLIST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SET_NETWORK_BLACKLIST
 - PNDIS_WWAN_SET_NETWORK_BLACKLIST
 - NDIS_WWAN_SET_NETWORK_BLACKLIST
---

# _NDIS_WWAN_SET_NETWORK_BLACKLIST structure


## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

The **NDIS_WWAN_SET_NETWORK_BLACKLIST** structure describes a list of network blacklist providers that a mobile broadband (MBB) device should use to overwrite any existing blacklist providers in the modem.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_NETWORK_BLACKLIST** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_NETWORK_BLACKLIST_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_NETWORK_BLACKLIST) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md).

### -field SetNetworkBlacklist

A formatted [**WWAN_NETWORK_BLACKLIST_INFO**](../wwan/ns-wwan-_wwan_network_blacklist_info.md) structure that contains the new list of network blacklist providers for the modem.

## -remarks

This structure is used in an [OID_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/oid-wwan-network-blacklist) Set request.

After completing the Set request, the modem should return an [NDIS_STATUS_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/ndis-status-wwan-network-blacklist) status notification as a response to inform the OS of the updated network blacklists.

## -see-also

[MB Network Blacklist Operations](/windows-hardware/drivers/network/mb-network-blacklist-operations)

[OID_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/oid-wwan-network-blacklist)

[NDIS_STATUS_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/ndis-status-wwan-network-blacklist)

[**WWAN_NETWORK_BLACKLIST_INFO**](../wwan/ns-wwan-_wwan_network_blacklist_info.md)

