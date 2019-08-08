---
UID: NF:netrxqueue.NetRxQueueGetExtension
title: NetRxQueueGetExtension function (netrxqueue.h)
description: The NetRxQueueGetExtension method retrieves a packet extension for all packets in a receive (Rx) queue.
tech.root: netvista
ms.assetid: a3581073-6875-478b-88c6-ca753cca08b2
ms.date: 01/31/2019
ms.topic: function
f1_keywords:
 - "netrxqueue/NetRxQueueCreate"
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
product:
- Windows
targetos: Windows

---

# NetRxQueueGetExtension function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRxQueueGetExtension** method retrieves a packet extension for all packets in a receive (Rx) queue.

## -parameters

### -param PacketQueue

The receive queue object.

### -param Query

A pointer to a driver-allocated and initialized [**NET_PACKET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_packet_extension_query.md) structure that contains information about the desired packet extension.

### -param Extension

A handle to a driver-allocated [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that receives the packet extension.

## -returns

None.

## -remarks

Client drivers typically call this method from their *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function after queue creation. To prevent frequent extension queries, store the extension returned by this method in your queue context space.

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
