---
UID: NF:nblhash.NET_BUFFER_LIST_GET_HASH_FUNCTION
title: NET_BUFFER_LIST_GET_HASH_FUNCTION
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_LIST_GET_HASH_FUNCTION macro gets the hash function information from a NET_BUFFER_LIST structure.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblhash.h
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
 - nblhash.h
api_name:
 - NET_BUFFER_LIST_GET_HASH_FUNCTION
f1_keywords:
 - NET_BUFFER_LIST_GET_HASH_FUNCTION
 - nblhash/NET_BUFFER_LIST_GET_HASH_FUNCTION
dev_langs:
 - c++
---


# NET_BUFFER_LIST_GET_HASH_FUNCTION macro


## -description

The **NET_BUFFER_LIST_GET_HASH_FUNCTION** macro gets the hash function information from a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_GET_HASH_FUNCTION** returns the hash function used. For more information, see [RSS Hashing Functions](/windows-hardware/drivers/network/rss-hashing-functions).

The hash function can be one of the following values:

- **NdisHashFunctionToeplitz**
- **NdisHashFunctionReserved1**
- **NdisHashFunctionReserved2**
- **NdisHashFunctionReserved3**

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hashing function to calculate an RSS hash value.

For more information about the hashing functions, see [RSS Hashing Functions](/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

