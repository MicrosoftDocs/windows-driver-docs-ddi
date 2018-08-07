---
UID: NF:netrxqueue.NetRxQueueGetPacketExtensionOffset
title: NetRxQueueGetPacketExtensionOffset function
author: windows-driver-content
description: The NetRxQueueGetPacketExtensionOffset method retrieves the offset, in bytes, to a packet extension for all packets in a receive (Rx) queue.
ms.assetid: a3581073-6875-478b-88c6-ca753cca08b2
ms.author: windowsdriverdev
ms.date: 03/02/2018
ms.topic: function
ms.keywords: NetRxQueueGetPacketExtensionOffset
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
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
-	NetRxQueueGetPacketExtensionOffset
product:
-	Windows
targetos: Windows

---

# NetRxQueueGetPacketExtensionOffset function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetRxQueueGetPacketExtensionOffset** method retrieves the offset, in bytes, to a packet extension for all packets in a receive (Rx) queue.

## -parameters

### -param NetRxQueue
The receive queue object.

### -param ExtensionToGet
A pointer to a driver-allocated and initialized [NET_PACKET_EXTENSION_QUERY](../netadapterpacket/ns-netadapterpacket-_net_packet_extension_query.md) structure that contains information about the desired packet extension.

## -returns
Returns the offset to the desired extension from the beginning of the packet descriptor. This value is for all packets in this queue.

## -remarks
Client drivers typically call this method from their *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function after queue creation. To prevent frequent offset queries, store the offset returned by this method in your queue context space.



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)