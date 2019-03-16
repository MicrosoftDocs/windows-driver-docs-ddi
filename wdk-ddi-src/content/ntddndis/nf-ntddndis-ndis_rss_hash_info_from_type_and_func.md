---
UID: NF:ntddndis.NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
title: NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC macro (ntddndis.h)
description: The NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC macro combines a hash type and hash function into hash information and sets the HashInformation member in the NDIS_RECEIVE_SCALE_PARAMETERS structure.
tech.root: netvista
ms.assetid: f25dc03e-97b0-43fa-93d4-dd58090b530a
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
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
- NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC
product:
- Windows
targetos: Windows

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

For more information about hash types and the valid combinations of these flags, see [RSS Hashing Types](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-types).

### -param _HashFunction

The hash function that is used.

The hash function can be one of the following values:

- **NdisHashFunctionToeplitz**
- **NdisHashFunctionReserved1**
- **NdisHashFunctionReserved2**
- **NdisHashFunctionReserved3**

For more information about the hashing functions, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

## -returns

**NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC** returns the hash information that results from combining the specified hash type and hash function.

## -remarks

Use the [**NDIS_RSS_HASH_TYPE_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_type_from_hash_info.md) and [**NDIS_RSS_HASH_FUNC_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_func_from_hash_info.md) macros to get the hash type and hash function from the hash information.

A NIC (or its miniport driver) uses the receive side scaling (RSS) hash type to identify the portion of received network data that is used to calculate an RSS hash value.

For more information about the hash type, see [RSS Hashing Types](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-types).

A NIC (or its miniport driver) uses the RSS hashing function to calculate an RSS hash value.

For more information about the hashing functions, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NDIS_RECEIVE_SCALE_PARAMETERS**](ns-ntddndis-_ndis_receive_scale_parameters.md)

[**NDIS_RSS_HASH_FUNC_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_func_from_hash_info.md)

[**NDIS_RSS_HASH_TYPE_FROM_HASH_INFO**](nf-ntddndis-ndis_rss_hash_type_from_hash_info.md)
