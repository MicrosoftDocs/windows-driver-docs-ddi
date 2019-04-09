---
UID: NF:ndis.NET_BUFFER_LIST_SET_HASH_FUNCTION
title: NET_BUFFER_LIST_SET_HASH_FUNCTION function (ndis.h)
description: The NET_BUFFER_LIST_SET_HASH_FUNCTION macro sets the hash function information in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: e586100e-39f4-4ecf-8f50-65470bc6d9d3
ms.date: 04/13/2018
ms.topic: function
ms.keywords: NET_BUFFER_LIST_SET_HASH_FUNCTION
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- NET_BUFFER_LIST_SET_HASH_FUNCTION
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_SET_HASH_FUNCTION function


## -description

The **NET_BUFFER_LIST_SET_HASH_FUNCTION** macro sets the hash function information in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _HashFunction

The hash function that is used. For more information, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

The hash function can be one of the following:

- **NdisHashFunctionToeplitz**
- **NdisHashFunctionReserved1**
- **NdisHashFunctionReserved2**
- **NdisHashFunctionReserved3**

## -returns

This macro does not return a value.

## -remarks

A NIC (or its miniport driver) uses the receive side scaling (RSS) hashing function to calculate an RSS hash value.

For more information about the hashing functions, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions).

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
