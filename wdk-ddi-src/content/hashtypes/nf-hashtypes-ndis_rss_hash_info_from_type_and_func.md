---
UID: NF:hashtypes.NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
title: NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC macro combines a hash type and hash function into hash information and sets the HashInformation member in the NDIS_RECEIVE_SCALE_PARAMETERS structure.
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
 - NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
f1_keywords:
 - NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
 - hashtypes/NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
dev_langs:
 - c++
---


# NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC macro


## -description

The **NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC** macro combines a hash type and hash function into hash information and sets the **HashInformation** member in the [**NDIS_RECEIVE_SCALE_PARAMETERS**](ns-ntddndis-_ndis_receive_scale_parameters.md) structure.

## -parameters

### -param _HashType

The hash type.

The hash type is an OR value of valid combinations of the following flags:

- NDIS_HASH_IPV4
- NDIS_HASH_TCP_IPV4
- NDIS_HASH_IPV6
- NDIS_HASH_TCP_IPV6
- NDIS_HASH_IPV6_EX
- NDIS_HASH_TCP_IPV6_EX

For more information about hash types and the valid combinations of these flags, see [RSS Hashing Types](/windows-hardware/drivers/network/rss-hashing-types).

### -param _HashFunction

The hash function that is used.

The hash function can be one of the following values:

- **NdisHashFunctionToeplitz**
- **NdisHashFunctionReserved1**
- **NdisHashFunctionReserved2**
- **NdisHashFunctionReserved3**

For more information about the hashing functions, see [RSS Hashing Functions](/windows-hardware/drivers/network/rss-hashing-functions).

## -returns

**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC** returns the hash information that results from combining the specified hash type and hash function.

## -remarks

Use the [**NDIS_RSS_HASH_TYPE_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_type_from_hash_info.md) and [**NDIS_RSS_HASH_FUNC_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_func_from_hash_info.md) macros to get the hash type and hash function from the hash information.

A NIC (or its miniport driver) uses the receive side scaling (RSS) hash type to identify the portion of received network data that is used to calculate an RSS hash value.

For more information about the hash type, see [RSS Hashing Types](/windows-hardware/drivers/network/rss-hashing-types).

A NIC (or its miniport driver) uses the RSS hashing function to calculate an RSS hash value.

For more information about the hashing functions, see [RSS Hashing Functions](/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NDIS_RECEIVE_SCALE_PARAMETERS**](ns-ntddndis-_ndis_receive_scale_parameters.md)

[**NDIS_RSS_HASH_FUNC_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_func_from_hash_info.md)

[**NDIS_RSS_HASH_TYPE_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_type_from_hash_info.md)

