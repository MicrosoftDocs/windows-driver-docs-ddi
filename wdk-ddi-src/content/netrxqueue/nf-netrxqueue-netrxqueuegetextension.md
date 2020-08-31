---
UID: NF:netrxqueue.NetRxQueueGetExtension
title: NetRxQueueGetExtension function (netrxqueue.h)
description: The NetRxQueueGetExtension function retrieves a packet extension for all packets in a receive (Rx) queue.
tech.root: netvista
ms.assetid: a3581073-6875-478b-88c6-ca753cca08b2
ms.date: 01/31/2019
keywords: ["NetRxQueueGetExtension function"]
f1_keywords:
 - "netrxqueue/NetRxQueueCreate"
 - "NetRxQueueCreate"
ms.keywords: NetRxQueueGetExtension
req.header: netrxqueue.h
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
- NetRxQueueGetExtension
targetos: Windows

---

# NetRxQueueGetExtension function


## -description


The **NetRxQueueGetExtension** function retrieves a packet extension for all packets in a receive (Rx) queue.

## -parameters

### -param PacketQueue

The receive queue object.

### -param Query

A pointer to a driver-allocated and initialized [**NET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_extension_query.md) structure that contains information about the desired packet extension.

### -param Extension

A handle to a driver-allocated [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that receives the packet extension.

## -remarks

Client drivers typically call this function from their *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function after queue creation. To prevent frequent extension queries, store the extension returned by this function in your queue context space.

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
