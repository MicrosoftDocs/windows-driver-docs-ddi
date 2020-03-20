---
UID: NF:ndis.NET_BUFFER_LIST_SET_HASH_VALUE
title: NET_BUFFER_LIST_SET_HASH_VALUE macro (ndis.h)
description: The NET_BUFFER_LIST_SET_HASH_VALUE macro sets the hash value information in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 4c72d349-dc74-42b5-ae97-2e68f18285fa
ms.date: 04/13/2018
keywords: ["NET_BUFFER_LIST_SET_HASH_VALUE macro"]
f1_keywords:
 - "ndis/NET_BUFFER_LIST_SET_HASH_VALUE"
ms.keywords: NET_BUFFER_LIST_SET_HASH_VALUE
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
- HeaderDef
api_location: 
- ndis.h
api_name: 
- NET_BUFFER_LIST_SET_HASH_VALUE
product:
- Windows
targetos: Windows

---

# NET_BUFFER_LIST_SET_HASH_VALUE macro


## -description

The **NET_BUFFER_LIST_SET_HASH_VALUE** macro sets the hash value information in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _HashValue

The hash value, which is formatted as a ULONG.

## -remarks

For more information about the hash value, see [RSS Hashing Functions](https://docs.microsoft.com/windows-hardware/drivers/network/rss-hashing-functions)

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
