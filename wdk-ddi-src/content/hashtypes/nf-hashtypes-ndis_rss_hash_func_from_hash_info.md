---
UID: NF:hashtypes.NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
title: NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_RSS_HASH_FUNC_FROM_HASH_INFO macro gets the hash function from the hash information.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/hashtypes.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - hashtypes.h
api_name:
 - NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
f1_keywords:
 - NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
 - hashtypes/NDIS_RSS_HASH_FUNC_FROM_HASH_INFO
dev_langs:
 - c++
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

For more information about the hashing functions, see [RSS Hashing Functions](/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC**](nf-ntddndis-ndis_rss_hash_info_from_type_and_func.md)