---
UID: NF:ntddndis.NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
title: NDIS_RSS_HASH_FUNC_FROM_HASH_INFO macro (ntddndis.h)
description: The NDIS_RSS_HASH_FUNC_FROM_HASH_INFO macro gets the hash function from the hash information.
tech.root: netvista
ms.assetid: 27fd758b-7b00-4ed7-81cb-6d4170a6a220
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntddndis.h
api_name: 
-	NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
product:
-	Windows
targetos: Windows

---

# NDIS_RSS_HASH_FUNC_FROM_HASH_INFO macro


## -description

The **NDIS_RSS_HASH_FUNC_FROM_HASH_INFO** macro gets the hash function from the hash information.

## -parameters

### -param _HashInfo

The hash information.

## -returns

**NDIS_RSS_HASH_FUNC_FROM_HASH_INFO** returns the hash function from the specified hash information. For more information about the hash information, see [**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC**](nf-ntddndis-ndis_rss_hash_info_from_type_and_func.md).

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hashing function to calculate an RSS hash value.

For more information about the hashing functions, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC**](nf-ntddndis-ndis_rss_hash_info_from_type_and_func.md)
