---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_ADVANCE
title: EVT_PACKET_QUEUE_ADVANCE
author: windows-driver-content
description: The EvtPacketQueueAdvance callback function is implemented by the client driver to process transmit or receive packets provided by NetAdapterCx.
ms.assetid: d4d6becc-ae41-451d-939d-c4169456adb7
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netpacketqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	netpacketqueue.h
api_name: 
-	EVT_PACKET_QUEUE_ADVANCE
product: Windows
targetos: Windows
---

# EVT_PACKET_QUEUE_ADVANCE callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtPacketQueueAdvance* callback function is implemented by the client driver to process transmit or receive packets provided by NetAdapterCx.

## -prototype

```C++
//Declaration

EVT_PACKET_QUEUE_ADVANCE EvtPacketQueueAdvance; 

// Definition

VOID EvtPacketQueueAdvance 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue

A handle to a packet queue.

## -returns

This callback function does not return a value.

## -remarks

Register this callback function in your *EVT_NET_ADAPTER_CREATE_TX(RX)QUEUE* callback. Set the appropriate member of a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure when you are initializing the structure with [**NET_PACKET_QUEUE_CONFIG_INIT**](nf-netpacketqueue-net_packet_queue_config_init.md), then call **NetTx(Rx)QueueCreate**.

NetAdapterCx serializes this callback function along with the packet queue's [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md) and [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md) callback functions.

For more info and a diagram showing the NetAdapterCx data path polling model, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

### Transmit queue example

For a transmit queue, the client retrieves packets from the queue, programs the hardware to send the data, and returns any completed packets.

To return packets, call [NetRingBufferIncrementIndex](../netringbuffer/nf-netringbuffer-netringbufferincrementindex.md), or use a helper method such as [NetRingBufferReturnCompletedPackets](../netadapterpacket/nf-netadapterpacket-netringbufferreturncompletedpackets.md).

The following example retrieves incoming transmit packets from the queue and immediately completes them.

```C++
VOID
MyEvtTxQueueAdvance(
	NETPACKETQUEUE TxQueue
)
{
    PCNET_DATAPATH_DESCRIPTOR descriptor = NetTxQueueGetDatapathDescriptor(TxQueue);
    NET_PACKET *netPacket;

    // Retrieve pointer to packet at the NextIndex value of the ring buffer

    while ((netPacket = NetRingBufferGetNextPacket(descriptor)) != nullptr)
    {

        // Transmit the data
        netPacket->Completed = TRUE;

        // Increment NextIndex
        NetRingBufferAdvanceNextPacket(descriptor);
    }

    NetRingBufferReturnCompletedPackets(descriptor);
}
```

### Receive queue example

In this callback function, the client driver typically performs the following steps for a receive queue:

1. Call [**NetRxQueueGetDatapathDescriptor**](../netrxqueue/nf-netrxqueue-netrxqueuegetdatapathdescriptor.md) to retrieve the datapath descriptor associated with the receive queue.
2. Use the receive queue's datapath descriptor retrieve the packet ring buffer by calling [**NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER**](../netdatapathdescriptor/nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md).
3. Program packets returned by the OS to hardware. The window includes packets starting from **NextIndex** up until **EndIndex**.
	1. Iterate until **NextIndex** matches **EndIndex**, or the hardware stops accepting new descriptors.
	2. Call [**NetRingBufferGetPacketAtIndex**](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md) to retrieve the packet at **NextIndex**.
	3. Free any resources associated with the packet that may have been allocated the last time the descriptor was handed to the OS.
	4. Program the packet to the associated hardware receive queue.
	5. Call [**NetRingBufferIncrementIndex**](../netringbuffer/nf-netringbuffer-netringbufferincrementindex.md) to advance **NextIndex**. This routine handles ring buffer wrap around.

	```C++
	VOID
	MyEvtRxQueueAdvance(
		NETPACKETQUEUE RxQueue
	)
	{
		// Optional: retrieve the queue's WDF context
		MY_RX_QUEUE_CONTEXT *rxContext = GetRxQueueContext(RxQueue);

		// Tip: store a reference to the datapath descriptor in the receive context to reduce
		// calls out of the driver
		PCNET_DATAPATH_DESCRIPTOR descriptor = NetRxQueueGetDatapathDescriptor(RxQueue);
		NET_RING_BUFFER* ringBuffer = NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER(descriptor);

		// Move returned packet descriptors back to the hardware queue
		while (ringBuffer->NextIndex != ringBuffer->EndIndex)
		{
			NET_PACKET* netPacket =
				NetRingBufferGetPacketAtIndex(descriptor, ringBuffer->NextIndex);

			// Optional: retrieve the queue's packet context
			MY_RX_PACKET_CONTEXT* packetContext = GetRxPacketContext(netPacket);

			// Free resources associated with the packet
			...

			// program the NET_PACKET to hardware
			...

			// Return the packet to the available descriptor queue
			ringBuffer->NextIndex =
				NetRingBufferIncrementIndex(ringBuffer, ringBuffer->NextIndex);
		}

		// Indicate received packets (see next example)
		...
	}
	```
3. Return completed packets to the OS by incrementing **BeginIndex**. If the driver completes packets asynchronously in software (for example, a USB bus completes receive requests asynchronously), use the **Completed** flag on the packet to track completion.

	```C++
	while (ringBuffer->BeginIndex != ringBuffer->NextIndex)
		{
			NET_PACKET *netPacket =
				NetRingBufferGetPacketAtIndex(descriptor, ringBuffer->BeginIndex);

			// optional: retrieve queue's packet context
			MY_RX_PACKET_CONTEXT *packetContext = GetRxPacketContext(netPacket);

			// Optional: When an asynchronous send operation completes, update the
			// Completed flag on the packet. In the Advance callback, return each
			// packet starting at BeginIndex until a packet not marked as Completed
			// is reached, or EndIndex is reached. Packets must be returned
			// sequentially, so indication must stop as soon as the first
			// non-Completed packet is reached.
			//
			// The Completed flag is not used by the OS, so the device is free to
			// use this flag.
			if (!netPacket->Completed)
				break;

			ringBuffer->BeginIndex =
				NetRingBufferIncrementIndex(ringBuffer, ringBuffer->BeginIndex);
		}
	```

For OS-allocated and attached receive buffers, client drivers must perform these actions:

- Client drivers must not modify the **VirtualAddress** of any fragment and should treat it as read-only.
- Client drivers must set the **Offset** field of the fragment.
- Client drivers must set the **ValidLength** field of the fragment.
- Client drivers should check to that **ValidLength** \<= **Capacity**.

The purpose of the **Offset** field in each fragment is to reserve space for upper layers such as filter or protocol drivers. For example, this permits an upper layer component that might want to encap this packet to do so in place. 

The framework ensures that the total size of each fragment buffer meets both the requirements of client drivers and of upper layers. For example, if a client driver's device has a maximum transmission unit (MTU) size of 1500 bytes and it needs 32 additional bytes per buffer for metadata, the client driver should report 1532 as the **MaximumFragmentBufferSize**. Then, because the `TCPIP.sys` upper layer protocol driver requires 8 bytes of header room per packet, the framework allocates 1540 bytes per receive buffer (1532 + 8). Client drivers should receive into the base address of the fragment + 8 (the extra offset for TCPIP), then process the 32 bytes of metadata that is meaningful to them. Finally, before indicating the packet up the stack, client drivers should update the **Offset** to be 40 (8 + 32), which is where the actual IP packet starts.

For more information and diagrams about packet and fragment descriptors, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions).

## -see-also

[*EVT_NET_ADAPTER_CREATE_RXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)

[*EVT_NET_ADAPTER_CREATE_TXQUEUE*](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[*EVT_PACKET_QUEUE_START*](nc-netpacketqueue-evt_packet_queue_start.md)

[*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_set_notification_enabled.md)

[*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_cancel.md)

[*EVT_PACKET_QUEUE_STOP*](nc-netpacketqueue-evt_packet_queue_stop.md)