---
UID: NF:nettxqueue.NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN
title: NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN macro
author: windows-driver-content
description: The NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN macro retrieves a NET_PACKET_CONTEXT_TOKEN for a NET_PACKET context based on the supplied context type name.
ms.assetid: 84f9b929-da1e-4da9-bbba-33be1f9bb5c6
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: macro
ms.keywords: NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN
req.header: nettxqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
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
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	nettxqueue.h
apiname: 
-	NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN macro


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN** macro retrieves a **NET_PACKET_CONTEXT_TOKEN** for a [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) context based on the supplied context type name.

## -parameters

### -param _txqueue
A handle to the NETTXQUEUE object.

### -param _contexttype
The structure type name of a driver-defined structure that describes the contents of the packet's context space.

## -remarks
In NetAdapterCx 1.1, the ability to add more than one packet context was introduced, meaning queues with more than one packet per context now require a **NET_PACKET_CONTEXT_TOKEN** to identify and retrieve each context. Call **NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN** to retrieve the token for a context type if your transmit queue uses more than one context per packet.

For an example of how to use this macro to retrieve a packet context token, see [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](../netadapterpacket/nf-netadapterpacket-net_packet_declare_context_type_with_name.md).

The minimum NetAdapterCx version for **NET_TXQUEUE_GET_PACKET_CONTEXT_TOKEN** is 1.1.

## -see-also