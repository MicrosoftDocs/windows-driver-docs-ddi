---
UID: NF:nettxqueue.NetTxQueueInitAddPacketContextAttributes
title: NetTxQueueInitAddPacketContextAttributes function
author: windows-driver-content
description: The NetTxQueueInitAddPacketContextAttributes method adds an initialized NET_PACKET_CONTEXT_ATTRIBUTES structure to a transmit queue's packet context space.
tech.root: netvista
ms.assetid: 266b8208-f030-4216-9967-7e201aaa607b
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetTxQueueInitAddPacketContextAttributes
req.header: nettxqueue.h
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
-	nettxqueue.h
apiname: 
-	NetTxQueueInitAddPacketContextAttributes
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetTxQueueInitAddPacketContextAttributes function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetTxQueueInitAddPacketContextAttributes** method adds an initialized [NET_PACKET_CONTEXT_ATTRIBUTES](../netadapterpacket/ns-netadapterpacket-_net_packet_context_attributes.md) structure to a transmit queue's packet context space.

## -parameters

### -param NetTxQueueInit
A pointer to a **NETTXQUEUE_INIT** structure that the client driver received in *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)*.

### -param PacketContextAttributes
A pointer to an initialized [NET_PACKET_CONTEXT_ATTRIBUTES](../netadapterpacket/ns-netadapterpacket-_net_packet_context_attributes.md) structure that represents attributes for the context space of each [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) in this queue.

## -returns
If the operation is successful, this method must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate NTSTATUS error code.

## -remarks
The **NETTXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to **WDFDEVICE_INIT**. The client driver receives a pointer to the **NETTXQUEUE_INIT** object in its *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md) callback function, where this method is called to add context attributes to the queue for each packet context the driver has created.



## -see-also
