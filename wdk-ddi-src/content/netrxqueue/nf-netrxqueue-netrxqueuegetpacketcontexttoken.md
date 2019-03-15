---
UID: NF:netrxqueue.NetRxQueueGetPacketContextToken
title: NetRxQueueGetPacketContextToken function (netrxqueue.h)
description: The NetRxQueueGetPacketContextToken method retrieves a NET_PACKET_CONTEXT_TOKEN for a NET_PACKET context on a receive queue. This method is reserved for NetAdapterCx. Client drivers must not call this method directly.
tech.root: netvista
ms.assetid: 4e4d870f-2be6-4936-a76b-226bafb5bb90
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueGetPacketContextToken
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrxqueue.h
api_name: 
- NetRxQueueGetPacketContextToken
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRxQueueGetPacketContextToken function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The NetRxQueueGetPacketContextToken method retrieves a **NET_PACKET_CONTEXT_TOKEN** for a [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) context on a receive queue.

> [!WARNING]
> This method is reserved for NetAdapterCx. Client drivers must not call this method directly.

## -parameters

### -param NetRxQueue
Reserved.

### -param ContextTypeInfo
Reserved.

## -returns
Returns a pointer to the **NET_PACKET_CONTEXT_TOKEN**.

## -remarks


## -see-also
