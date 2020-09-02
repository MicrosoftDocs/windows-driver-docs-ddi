---
UID: NS:ndiswwan._NDIS_WWAN_NETWORK_BLACKLIST
title: _NDIS_WWAN_NETWORK_BLACKLIST (ndiswwan.h)
description: The NDIS_WWAN_NETWORK_BLACKLIST structure describes a mobile broadband (MBB) device's network blacklists.
tech.root: netvista
ms.assetid: 0d203d04-dcd7-46d6-9dc0-62880068949d
ms.date: 08/21/2018
keywords: ["NDIS_WWAN_NETWORK_BLACKLIST structure"]
ms.keywords: _NDIS_WWAN_NETWORK_BLACKLIST, NDIS_WWAN_NETWORK_BLACKLIST, *PNDIS_WWAN_NETWORK_BLACKLIST,
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
req.typenames: NDIS_WWAN_NETWORK_BLACKLIST, *PNDIS_WWAN_NETWORK_BLACKLIST
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_WWAN_NETWORK_BLACKLIST
 - ndiswwan/_NDIS_WWAN_NETWORK_BLACKLIST
 - PNDIS_WWAN_NETWORK_BLACKLIST
 - ndiswwan/PNDIS_WWAN_NETWORK_BLACKLIST
 - NDIS_WWAN_NETWORK_BLACKLIST
 - ndiswwan/NDIS_WWAN_NETWORK_BLACKLIST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_NETWORK_BLACKLIST
product:
 - Windows
---

# _NDIS_WWAN_NETWORK_BLACKLIST structure


## -description

The **NDIS_WWAN_NETWORK_BLACKLIST** structure describes a mobile broadband (MBB) device's list of network blacklist providers.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_NETWORK_BLACKLIST** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_NETWORK_BLACKLIST_REVISION_1 |
| Size | sizeof(NDIS_WWAN_NETWORK_BLACKLIST) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |

### -field NetworkBlacklistInfo

 
A formatted [**WWAN_NETWORK_BLACKLIST_INFO**](../wwan/ns-wwan-_wwan_network_blacklist_info.md) structure that contains a list of network blacklist providers for the modem.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-network-blacklist) status notification in response to a previous [OID_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-network-blacklist) Query or Set request.

## -see-also

[MB Network Blacklist Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-network-blacklist-operations)

[OID_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-network-blacklist)

[NDIS_STATUS_WWAN_NETWORK_BLACKLIST](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-network-blacklist)

[**WWAN_NETWORK_BLACKLIST_INFO**](../wwan/ns-wwan-_wwan_network_blacklist_info.md)

