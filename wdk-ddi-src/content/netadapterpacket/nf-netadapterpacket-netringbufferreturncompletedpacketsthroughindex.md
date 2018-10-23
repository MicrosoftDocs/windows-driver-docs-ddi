---
UID: NF:netadapterpacket.NetRingBufferReturnCompletedPacketsThroughIndex
title: NetRingBufferReturnCompletedPacketsThroughIndex function
author: windows-driver-content
description: Returns all packets in a datapath queue's packet ring buffer that have the Completed flag set, up to a specified range.
tech.root: netvista
ms.assetid: d9d11975-4c19-4c3e-9de7-dafc2d37d64b
ms.date: 07/13/2018
ms.topic: function
ms.keywords: NetRingBufferReturnCompletedPacketsThroughIndex
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
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
-	netadapterpacket.h
apiname: 
-	NetRingBufferReturnCompletedPacketsThroughIndex
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRingBufferReturnCompletedPacketsThroughIndex function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Returns all packets in a datapath queue's packet ring buffer that have the **Completed** flag set, up to a specified range.

## -parameters

### -param Descriptor

A pointer to the datapath queue's [**NET_DATAPATH_DESCRIPTOR**](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

### -param EndIndex

The index of the last [**NET_PACKET**](../netpacket/ns-netpacket-_net_packet.md) to be considered for completion. This index is exclusive of the range, so the packet at this index value will not be completed.

### -param BatchSize

The number of packets to return in this batch.

## -returns
This method does not return a value.

## -remarks

> [!IMPORTANT]
> This method must only be called within the context of *EvtPacketQueueAdvance* or *EvtPacketQueueCancel*. At no other time should the client driver call this helper method, or any other helper method, that modifies the **BeginIndex** of either the fragment or packet ring buffers.

Call **NetTx(Rx)QueueGetDatapathDescriptor** to obtain the datapath descriptor structure for the queue with which you're working.

The NetAdapter data path requires packets to be completed in the order in which they are given to your driver. If your driver can complete some packets out of order, you can use **NetRingBufferReturnCompletedPacketsThroughIndex** to simplify your completion path.

To use this convenience function, first set the **Completed** flag on the first fragment of all packets with which your driver is finished, whether the packets were processed successfully or not. Then, call **NetRingBufferReturnCompletedPacketsThroughIndex** to batch the completion of all consecutive packets for which the first fragment has the **Completed** flag set.

**NetRingBufferReturnCompletedPacketsThroughIndex** completes packets by writing a new value to the **BeginIndex** of the ring buffer.

If you always complete packets in order, it is more efficient to write to **BeginIndex** directly, rather than using the **Completed** flag with **NetRingBufferReturnCompletedPacketsThroughIndex**.

Typically, you would call **NetRingBufferReturnCompletedPacketsThroughIndex** once just before returning from [*EVT_PACKET_QUEUE_ADVANCE*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_advance.md). There's no advantage to calling **NetRingBufferReturnCompletedPacketsThroughIndex** more than once per *Advance* call because the API is designed for batching.

The [**NetRingBufferReturnCompletedPackets**](nf-netadapterpacket-netringbufferreturncompletedpackets.md) routine is similar, but examines all packets owned by your driver. **NetRingBufferReturnCompletedPacketsThroughIndex** allows you to limit the search to a specific range of packets owned by your driver. If you don't need to control the exact range of packets that are completed, you can use the simpler method [**NetRingBufferReturnCompletedPackets**](nf-netadapterpacket-netringbufferreturncompletedpackets.md) instead of **NetRingBufferReturnCompletedPacketsThroughIndex**.

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).


## -see-also
