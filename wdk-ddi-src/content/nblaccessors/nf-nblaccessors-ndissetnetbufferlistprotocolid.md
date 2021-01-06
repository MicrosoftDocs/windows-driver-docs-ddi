---
UID: NF:nblaccessors.NdisSetNetBufferListProtocolId
title: NdisSetNetBufferListProtocolId
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisSetNetBufferListProtocolId macro sets the protocol identifier in the NetBufferListInfo member of a NET_BUFFER_LIST structure.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nblaccessors.h
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
 - nblaccessors.h
api_name:
 - NdisSetNetBufferListProtocolId
f1_keywords:
 - NdisSetNetBufferListProtocolId
 - nblaccessors/NdisSetNetBufferListProtocolId
dev_langs:
 - c++
---

# NdisSetNetBufferListProtocolId macro


## -description

The **NdisSetNetBufferListProtocolId** macro sets the protocol identifier in the **NetBufferListInfo** member of a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

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

Drivers that create [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structures should set the protocol identifier by calling the **NdisSetNetBufferListProtocolId** macro or by associating an identifier with a **NET_BUFFER_LIST** pool.

To associate a protocol identifier with a **NET_BUFFER_LIST** pool, call the [**NdisAllocateNetBufferListPool**](nf-ndis-ndisallocatenetbufferlistpool.md) function and specify the protocol identifier in the **ProtocolId** member of the [**NET_BUFFER_LIST_POOL_PARAMETERS**](ns-ndis-_net_buffer_list_pool_parameters.md) structure.

Miniport, filter, and intermediate drivers set the protocol identifier to zero.

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NET_BUFFER_LIST_POOL_PARAMETERS**](ns-ndis-_net_buffer_list_pool_parameters.md)

[**NdisAllocateNetBufferListPool**](nf-ndis-ndisallocatenetbufferlistpool.md)

[**NdisGetNetBufferListProtocolId**](nf-ndis-ndisgetnetbufferlistprotocolid.md)

