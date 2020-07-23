---
UID: NF:ntddndis.NDIS_RSS_HASH_TYPE_FROM_HASH_INFO
title: NDIS_RSS_HASH_TYPE_FROM_HASH_INFO macro (ntddndis.h)
description: The NDIS_RSS_HASH_TYPE_FROM_HASH_INFO macro gets the hash type from the hash information.
tech.root: netvista
ms.assetid: 348687af-4632-4dad-a62a-0bc4e4c62415
ms.date: 04/16/2018
keywords: ["NDIS_RSS_HASH_TYPE_FROM_HASH_INFO macro"]
f1_keywords:
 - "ntddndis/NDIS_RSS_HASH_TYPE_FROM_HASH_INFO"
 - "NDIS_RSS_HASH_TYPE_FROM_HASH_INFO"
ms.keywords: NDIS_RSS_HASH_TYPE_FROM_HASH_INFO
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddndis.h
api_name: 
- NDIS_RSS_HASH_TYPE_FROM_HASH_INFO
targetos: Windows

---

# NDIS_RSS_HASH_TYPE_FROM_HASH_INFO macro


## -description

The **NDIS_RSS_HASH_TYPE_FROM_HASH_INFO** macro gets the hash type from the hash information.

## -parameters

### -param _HashInfo

The hash information. For more information about the hash information, see [**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC**](nf-ntddndis-ndis_rss_hash_info_from_type_and_func.md).

## -returns

NDIS_RSS_HASH_TYPE_FROM_HASH_INFO returns the hash type from the specified hash information. For more information about the hash type, see [RSS Hashing Types](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-types).

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hash type to identify the portion of received network data that is used to calculate an RSS hash value.

For more information about the hash type, see [RSS Hashing Types](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-types).

## -see-also

[**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC**](nf-ntddndis-ndis_rss_hash_info_from_type_and_func.md)
