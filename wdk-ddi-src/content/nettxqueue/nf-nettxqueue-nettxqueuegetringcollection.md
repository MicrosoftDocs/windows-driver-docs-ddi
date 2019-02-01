---
UID: NF:nettxqueue.NetTxQueueGetRingCollection
title: NetTxQueueGetRingCollection function (nettxqueue.h)
description: The NetTxQueueGetRingCollection method retrieves the NET_DATAPATH_DESCRIPTOR structure for a transmit (Tx) queue.
tech.root: netvista
ms.assetid: 0767d0c0-d648-4dca-a664-a514de495c3d
ms.date: 01/31/2019
ms.topic: function
ms.keywords: NetTxQueueGetRingCollection
req.header: nettxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetTxQueueGetRingCollection
product:
-	Windows
targetos: Windows

---

# NetTxQueueGetRingCollection function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetTxQueueGetRingCollection** method retrieves the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure for a transmit (Tx) queue.

## -parameters

### -param PacketQueue

A pointer to a NetAdapterCx-allocated **NETPACKETQUEUE** structure. The client driver receives a pointer to this **NETPACKETQUEUE** structure in its *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function.

## -returns

Returns a pointer to the queue's [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure.

## -remarks

Use the [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure returned by this method to access a transmit queue's net rings.

## -see-also
