---
UID: NF:ndis.NET_BUFFER_LIST_GET_HASH_TYPE
title: NET_BUFFER_LIST_GET_HASH_TYPE macro
author: windows-driver-content
description: The NET_BUFFER_LIST_GET_HASH_TYPE macro gets the hash type information from a NET_BUFFER_LIST structure.
ms.assetid: 982ec1c3-a6d9-4863-b5af-63c01c929234
ms.author: windowsdriverdev
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NET_BUFFER_LIST_GET_HASH_TYPE
req.header: ndis.h
req.include-header:
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
-	ndis.h
api_name: 
-	NET_BUFFER_LIST_GET_HASH_TYPE
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_LIST_GET_HASH_TYPE macro


## -description

The **NET_BUFFER_LIST_GET_HASH_TYPE** macro gets the hash type information from a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_GET_HASH_TYPE** returns the hash type of the specified [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

The hash type is an OR value of valid combinations of the following flags:

- NDIS_HASH_IPV4
- NDIS_HASH_TCP_IPV4
- NDIS_HASH_IPV6
- NDIS_HASH_TCP_IPV6
- NDIS_HASH_IPV6_EX
- NDIS_HASH_TCP_IPV6_EX

For more information about hash types and the valid combinations of these flags, see [RSS Hashing Types](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-types)).

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hash type to identify the portion of received network data that is used to calculate an RSS hash value.

For more information about the hash type, see [RSS Hashing Types](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-types).

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)