---
UID: NF:nettxqueue.NetTxQueueGetPacketExtensionOffset
title: NetTxQueueGetPacketExtensionOffset function
author: windows-driver-content
description: The NetTxQueueGetPacketExtensionOffset method retrieves the offset, in bytes, to a packet extension for all packets in a transmit (Tx) queue.
ms.assetid: f7e9b686-a38a-47dd-9872-9ebeca533a3a
ms.author: windowsdriverdev
ms.date: 07/13/2018
ms.topic: function
ms.keywords: NetTxQueueGetPacketExtensionOffset
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetTxQueueGetPacketExtensionOffset
product: Windows
targetos: Windows

---

# NetTxQueueGetPacketExtensionOffset function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetTxQueueGetPacketExtensionOffset** method retrieves the offset, in bytes, to a packet extension for all packets in a transmit (Tx) queue.

## -parameters

### -param NetTxQueue
The transmit queue object.

### -param ExtensionToGet
A pointer to a driver-allocated and initialized [**NET_PACKET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_packet_extension_query.md) structure that contains information about the desired packet extension.

## -returns
Returns the offset to the desired extension from the beginning of the packet descriptor. This value is for all packets in this queue.

## -remarks
Client drivers typically call this method from their *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* callback function after queue creation. To prevent frequent offset queries, store the offset returned by this method in your queue context space.



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)