---
UID: NF:ndis.NET_BUFFER_LIST_RECEIVE_FILTER_ID
title: NET_BUFFER_LIST_RECEIVE_FILTER_ID macro (ndis.h)
description: The NET_BUFFER_LIST_RECEIVE_FILTER_ID macro gets a receive filter identifier from the out-of-band (OOB) data in a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 4c419caa-e514-466e-a3d5-058ae12b8f3a
ms.date: 04/13/2018
keywords: ["NET_BUFFER_LIST_RECEIVE_FILTER_ID macro"]
f1_keywords:
 - "ndis/NET_BUFFER_LIST_RECEIVE_FILTER_ID"
 - "NET_BUFFER_LIST_RECEIVE_FILTER_ID"
ms.keywords: NET_BUFFER_LIST_RECEIVE_FILTER_ID
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- NET_BUFFER_LIST_RECEIVE_FILTER_ID
targetos: Windows

---

# NET_BUFFER_LIST_RECEIVE_FILTER_ID macro


## -description

The **NET_BUFFER_LIST_RECEIVE_FILTER_ID** macro gets a receive filter identifier from the out-of-band (OOB) data in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_RECEIVE_FILTER_ID** returns a USHORT value for a receive filter identifier.

## -remarks

Any NDIS 6.20 or later driver can use **NET_BUFFER_LIST_RECEIVE_FILTER_ID** to get the receive filter identifier from a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure. 

**NET_BUFFER_LIST_RECEIVE_FILTER_ID** gets the receive filter identifier from the **FilterId** member of the [**NDIS_NET_BUFFER_LIST_FILTERING_INFO**](ns-ndis-_ndis_net_buffer_list_filtering_info.md) structure.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NDIS_NET_BUFFER_LIST_FILTERING_INFO**](ns-ndis-_ndis_net_buffer_list_filtering_info.md)
