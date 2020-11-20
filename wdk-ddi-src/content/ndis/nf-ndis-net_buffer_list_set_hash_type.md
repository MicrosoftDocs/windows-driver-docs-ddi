---
UID: NF:ndis.NET_BUFFER_LIST_SET_HASH_TYPE
title: NET_BUFFER_LIST_SET_HASH_TYPE function (ndis.h)
description: The NET_BUFFER_LIST_SET_HASH_TYPE macro sets the hash type information in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 15fe028f-90ad-4759-9bf4-17192cfa25f7
ms.date: 04/13/2018
keywords: ["NET_BUFFER_LIST_SET_HASH_TYPE function"]
ms.keywords: NET_BUFFER_LIST_SET_HASH_TYPE
req.header: ndis.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
targetos: Windows
f1_keywords:
 - NET_BUFFER_LIST_SET_HASH_TYPE
 - ndis/NET_BUFFER_LIST_SET_HASH_TYPE
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NET_BUFFER_LIST_SET_HASH_TYPE
---

# NET_BUFFER_LIST_SET_HASH_TYPE function


## -description

The **NET_BUFFER_LIST_SET_HASH_TYPE** macro sets the hash type information in a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

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

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hash type to identify the portion of received network data that is used to calculate an RSS hash value.

For more information about the hash type, see [RSS Hashing Types](/windows-hardware/drivers/network/rss-hashing-types).

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)