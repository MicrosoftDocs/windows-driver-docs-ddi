---
UID: NF:netrxqueue.NetRxQueueInitAddPacketContextAttributes
title: NetRxQueueInitAddPacketContextAttributes function (netrxqueue.h)
description: The NetRxQueueInitAddPacketContextAttributes method adds an initialized NET_PACKET_CONTEXT_ATTRIBUTES structure to a receive queue's packet context space.
tech.root: netvista
ms.assetid: 6bb92b58-bc85-402a-90d7-f1b4a0f4865b
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueInitAddPacketContextAttributes
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NetRxQueueInitAddPacketContextAttributes
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRxQueueInitAddPacketContextAttributes function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetRxQueueInitAddPacketContextAttributes** method adds an initialized [NET_PACKET_CONTEXT_ATTRIBUTES](../netadapterpacket/ns-netadapterpacket-_net_packet_context_attributes.md) structure to a receive queue's packet context space.

## -parameters

### -param NetRxQueueInit
A pointer to the **NETRXQUEUE_INIT** structure that the client driver received in *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*.

### -param PacketContextAttributes
A pointer to a driver-supplied, initialized [NET_PACKET_CONTEXT_ATTRIBUTES](../netadapterpacket/ns-netadapterpacket-_net_packet_context_attributes.md) structure that represents attributes for the context space of each [NET_PACKET](../packet/ns-packet-_net_packet.md) in this queue.


## -returns
If the operation is successful, this method returns STATUS_SUCCESS. Otherwise, an appropriate NTSTATUS error code.

## -remarks
The **NETRXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to **WDFDEVICE_INIT**. The client driver receives a pointer to the **NETRXQUEUE_INIT** object in its  *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function, where this method is called to add context attributes to the queue for each packet context context the driver has created.



## -see-also
