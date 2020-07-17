---
UID: NF:nettxqueue.NetTxQueueGetExtension
title: NetTxQueueGetExtension function (nettxqueue.h)
description: The NetTxQueueGetExtension method retrieves a packet extension for all packets in a transmit (Tx) queue.
tech.root: netvista
ms.assetid: f7e9b686-a38a-47dd-9872-9ebeca533a3a
ms.date: 01/31/2019
keywords: ["NetTxQueueGetExtension function"]
f1_keywords:
 - "nettxqueue/NetTxQueueCreate"
 - "NetTxQueueCreate"
ms.keywords: NetTxQueueGetExtension
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
- apiref
apitype: 
- DllExport
apilocation: 
- NtosKrnl.exe
apiname: 
- NetTxQueueGetExtension
product:
- Windows
targetos: Windows

---

# NetTxQueueGetExtension function


## -description


The **NetTxQueueGetExtension** method retrieves a packet extension for all packets in a transmit (Tx) queue.

## -parameters

### -param PacketQueue

The transmit queue object.

### -param Query

A pointer to a driver-allocated and initialized [**NET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_extension_query.md) structure that contains information about the desired packet extension.


### -param Extension

A handle to a driver-allocated [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that receives the packet extension.

## -remarks

Client drivers typically call this method from their *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function after queue creation. To prevent frequent extension queries, store the extension returned by this method in your queue context space.

For a code example of creating a transmit queue, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
