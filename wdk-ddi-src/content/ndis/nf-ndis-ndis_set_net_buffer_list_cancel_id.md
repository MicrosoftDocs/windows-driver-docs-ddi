---
UID: NF:ndis.NDIS_SET_NET_BUFFER_LIST_CANCEL_ID
title: NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro (ndis.h)
description: The NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro marks a NET_BUFFER_LIST structure with a cancellation identifier that a driver can later use to cancel the pending transmission of the associated data.
tech.root: netvista
ms.assetid: 200a8e6b-6cd5-4364-8004-b3c374775d2f
ms.date: 04/16/2018
ms.topic: macro
f1_keywords:
 - "ndis/NDIS_SET_NET_BUFFER_LIST_CANCEL_ID"
ms.keywords: NDIS_SET_NET_BUFFER_LIST_CANCEL_ID
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
- NDIS_SET_NET_BUFFER_LIST_CANCEL_ID
product:
- Windows
targetos: Windows

---

# NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro


## -description

The **NDIS_SET_NET_BUFFER_LIST_CANCEL_ID** macro marks a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure with a cancellation identifier that a driver can later use to cancel the pending transmission of the associated data.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _CancelId

A ULONG value that is a cancellation identifier for the **NET_BUFFER_LIST** structure.

## -remarks

An NDIS driver can call the **NDIS_SET_NET_BUFFER_LIST_CANCEL_ID** macro for each [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure that it passes to lower-level drivers for transmission. The **NDIS_SET_NET_BUFFER_LIST_CANCEL_ID** macro marks the specified NET_BUFFER_LIST structure with a cancellation identifier. Drivers must call the [**NdisGeneratePartialCancelId**](nf-ndis-ndisgeneratepartialcancelid.md) function to obtain a value that the driver must use as the high-order byte of a cancellation identifier.

To cancel send requests, filter drivers call the [**NdisFCancelSendNetBufferLists**](nf-ndis-ndisfcancelsendnetbufferlists.md) function. Other drivers call the [**NdisCancelSendNetBufferLists**](nf-ndis-ndiscancelsendnetbufferlists.md) function.

Drivers can call the [**NDIS_GET_NET_BUFFER_LIST_CANCEL_ID**](nf-ndis-ndis_get_net_buffer_list_cancel_id.md) macro to retrieve a cancellation identifier from a **NET_BUFFER_LIST** structure.

## -see-also

[**NdisCancelSendNetBufferLists**](nf-ndis-ndiscancelsendnetbufferlists.md)

[**NdisFCancelSendNetBufferLists**](nf-ndis-ndisfcancelsendnetbufferlists.md)

[**NdisGeneratePartialCancelId**](nf-ndis-ndisgeneratepartialcancelid.md)

[**NDIS_GET_NET_BUFFER_LIST_CANCEL_ID**](nf-ndis-ndis_get_net_buffer_list_cancel_id.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
