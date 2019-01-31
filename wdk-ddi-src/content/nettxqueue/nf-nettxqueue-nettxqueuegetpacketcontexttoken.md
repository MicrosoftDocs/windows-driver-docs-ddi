---
UID: NF:nettxqueue.NetTxQueueGetPacketContextToken
title: NetTxQueueGetPacketContextToken function (nettxqueue.h)
description: The NetTxQueueGetPacketContextToken method retrieves a NET_PACKET_CONTEXT_TOKEN for a NET_PACKET context on a transmit queue. This method is reserved for NetAdapterCx. Client drivers must not call this method directly.
tech.root: netvista
ms.assetid: 073d6da4-96ae-4dbd-8aa5-fe12e465af33
ms.date: 07/13/2018
ms.topic: function
ms.keywords: NetTxQueueGetPacketContextToken
req.header: nettxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	nettxqueue.h
apiname: 
-	NetTxQueueGetPacketContextToken
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetTxQueueGetPacketContextToken function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetTxQueueGetPacketContextToken** method retrieves a **NET_PACKET_CONTEXT_TOKEN** for a [NET_PACKET](../netpacket/../packet/ns-packet-_net_packet.md) context on a transmit queue.

> [!WARNING]
> This method is reserved for NetAdapterCx. Client drivers must not call this method directly.

## -parameters

### -param NetTxQueue
Reserved.

### -param ContextTypeInfo
Reserved.

## -returns
Returns a pointer to the **NET_PACKET_CONTEXT_TOKEN**.

## -remarks


## -see-also
