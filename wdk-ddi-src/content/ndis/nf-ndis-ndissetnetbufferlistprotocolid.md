---
UID: NF:ndis.NdisSetNetBufferListProtocolId
title: NdisSetNetBufferListProtocolId macro (ndis.h)
description: The NdisSetNetBufferListProtocolId macro sets the protocol identifier in the NetBufferListInfo member of a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: e2af0fa5-6f94-4406-a5c9-20f114316d6d
ms.date: 04/13/2018
keywords: ["NdisSetNetBufferListProtocolId macro"]
f1_keywords:
 - "ndis/NdisSetNetBufferListProtocolId"
ms.keywords: NdisSetNetBufferListProtocolId
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
- NdisSetNetBufferListProtocolId
product:
- Windows
targetos: Windows

---

# NdisSetNetBufferListProtocolId macro


## -description

The **NdisSetNetBufferListProtocolId** macro sets the protocol identifier in the **NetBufferListInfo** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _ProtocolId

A protocol identifier, as one of the following values:

NDIS_PROTOCOL_ID_DEFAULT  
A default protocol driver identifier.

NDIS_PROTOCOL_ID_TCP_IP  
The TCP/IP protocol.

NDIS_PROTOCOL_ID_IPX  
The IPX protocol.

NDIS_PROTOCOL_ID_NBF  
The NetBEUI protocol.

## -remarks

Drivers that create [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structures should set the protocol identifier by calling the **NdisSetNetBufferListProtocolId** macro or by associating an identifier with a **NET_BUFFER_LIST** pool.

To associate a protocol identifier with a **NET_BUFFER_LIST** pool, call the [**NdisAllocateNetBufferListPool**](nf-ndis-ndisallocatenetbufferlistpool.md) function and specify the protocol identifier in the **ProtocolId** member of the [**NET_BUFFER_LIST_POOL_PARAMETERS**](ns-ndis-_net_buffer_list_pool_parameters.md) structure.

Miniport, filter, and intermediate drivers set the protocol identifier to zero.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

[**NET_BUFFER_LIST_POOL_PARAMETERS**](ns-ndis-_net_buffer_list_pool_parameters.md)

[**NdisAllocateNetBufferListPool**](nf-ndis-ndisallocatenetbufferlistpool.md)

[**NdisGetNetBufferListProtocolId**](nf-ndis-ndisgetnetbufferlistprotocolid.md)
