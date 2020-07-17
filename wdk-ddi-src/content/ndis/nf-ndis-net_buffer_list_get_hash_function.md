---
UID: NF:ndis.NET_BUFFER_LIST_GET_HASH_FUNCTION
title: NET_BUFFER_LIST_GET_HASH_FUNCTION macro (ndis.h)
description: The NET_BUFFER_LIST_GET_HASH_FUNCTION macro gets the hash function information from a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 6ad6ab88-31e3-471a-9c21-a87c76b6654a
ms.date: 04/13/2018
keywords: ["NET_BUFFER_LIST_GET_HASH_FUNCTION macro"]
f1_keywords:
 - "ndis/NET_BUFFER_LIST_GET_HASH_FUNCTION"
 - "NET_BUFFER_LIST_GET_HASH_FUNCTION"
ms.keywords: NET_BUFFER_LIST_GET_HASH_FUNCTION
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
- apiref
api_type: 
- HeaderDef
api_location: 
- ndis.h
api_name: 
- NET_BUFFER_LIST_GET_HASH_FUNCTION
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_GET_HASH_FUNCTION macro


## -description

The **NET_BUFFER_LIST_GET_HASH_FUNCTION** macro gets the hash function information from a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_GET_HASH_FUNCTION** returns the hash function used. For more information, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

The hash function can be one of the following values:

- **NdisHashFunctionToeplitz**
- **NdisHashFunctionReserved1**
- **NdisHashFunctionReserved2**
- **NdisHashFunctionReserved3**

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hashing function to calculate an RSS hash value.

For more information about the hashing functions, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
