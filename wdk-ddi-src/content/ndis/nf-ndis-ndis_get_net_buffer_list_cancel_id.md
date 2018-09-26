---
UID: NF:ndis.NDIS_GET_NET_BUFFER_LIST_CANCEL_ID
title: NDIS_GET_NET_BUFFER_LIST_CANCEL_ID macro
author: windows-driver-content
description: The NDIS_GET_NET_BUFFER_LIST_CANCEL_ID macro gets the cancellation identifier from a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 803f83f9-0b3f-42a5-823c-dd5bbcf8f1a2
ms.author: windowsdriverdev
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_GET_NET_BUFFER_LIST_CANCEL_ID
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
-	NDIS_GET_NET_BUFFER_LIST_CANCEL_ID
product:
-	Windows
targetos: Windows

---

# NDIS_GET_NET_BUFFER_LIST_CANCEL_ID macro


## -description

The **NDIS_GET_NET_BUFFER_LIST_CANCEL_ID** macro gets the cancellation identifier from a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NDIS_GET_NET_BUFFER_LIST_CANCEL_ID** returns a ULONG value that is a cancellation identifier for the [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -remarks

To cancel send requests, filter drivers call the [**NdisFCancelSendNetBufferLists**](nf-ndis-ndisfcancelsendnetbufferlists.md) function. Other NDIS drivers call the [**NdisCancelSendNetBufferLists**](nf-ndis-ndiscancelsendnetbufferlists.md) function.

Drivers can call the [**NDIS_SET_NET_BUFFER_LIST_CANCEL_ID**](nf-ndis-ndis_set_net_buffer_list_cancel_id.md) macro to set a cancellation identifier in a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -see-also

[**NdisCancelSendNetBufferLists**](nf-ndis-ndiscancelsendnetbufferlists.md)

[**NdisFCancelSendNetBufferLists**](nf-ndis-ndisfcancelsendnetbufferlists.md)

[**NDIS_SET_NET_BUFFER_LIST_CANCEL_ID**](nf-ndis-ndis_set_net_buffer_list_cancel_id.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
