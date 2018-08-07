---
UID: NC:netrxqueue.EVT_RXQUEUE_ADVANCE
title: EVT_RXQUEUE_ADVANCE
author: windows-driver-content
description: Implemented by the client driver to process receive packets provided by NetAdapterCx.
ms.assetid: 866fe5d1-1cf1-4fd0-9d44-f9ea45d7e9d1
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netrxqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
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
-	UserDefined
apilocation: 
-	netrxqueue.h
apiname: 
-	EVT_RXQUEUE_ADVANCE
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# EVT_RXQUEUE_ADVANCE callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implemented by the client driver to process receive packets provided by NetAdapterCx.

## -prototype

```c++
//Declaration

EVT_RXQUEUE_ADVANCE EvtRxqueueAdvance; 

// Definition

VOID EvtRxqueueAdvance 
(
	_In_	NETRXQUEUE	RxQueue
)
{...}

typedef EVT_RXQUEUE_ADVANCE *PFN_RXQUEUE_ADVANCE;
```

## -parameters

### -param RxQueue 
A handle to a net receive queue.

## -returns

This callback function does not return a value.

## -remarks
Register this callback function in by setting the appropriate member of [NET_RX_QUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md), initializing the **NET_RX_QUEUE_CONFIG** structure with [NET_RXQUEUE_CONFIG_INIT](nf-netrxqueue-net_rxqueue_config_init.md), then calling [NetRxQueueCreate](nf-netrxqueue-netrxqueuecreate.md).
	
NetAdapterCx serializes this callback function along with the receive queue's *[EVT_RXQUEUE_CANCEL](nc-netrxqueue-evt_rxqueue_cancel.md)* and *[EVT_RXQUEUE_SET_NOTIFICATION_ENABLED](nc-netrxqueue-evt_rxqueue_set_notification_enabled.md)* callback functions.

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).



### Example

In this callback function, the client driver typically performs the following steps:

1. Call [NetRxQueueGetDatapathDescriptor](nf-netrxqueue-netrxqueuegetdatapathdescriptor.md) to retrieve the datapath descriptor associated with the receive queue.
2. Use the receive queue's datapath descriptor retrieve the packet ring buffer by calling [NET_DATAPATH_DESCRIPTOR_GET_PACKET_RING_BUFFER](../netdatapathdescriptor/nf-netdatapathdescriptor-net_datapath_descriptor_get_packet_ring_buffer.md).
3. Program packets returned by the OS to hardware. The window includes packets starting from **NextIndex** up until **EndIndex**.
	1. Iterate until **NextIndex** matches **EndIndex**, or the hardware stops accepting new descriptors.
	2. Call [NetRingBufferGetPacketAtIndex](../netadapterpacket/nf-netadapterpacket-netringbuffergetpacketatindex.md) to retrieve the packet at **NextIndex**.
	3. Free any resources associated with the packet that may have been allocated the last time the descriptor was handed to the OS.
	4. Program the packet to the associated hardware receive queue.
	5. Call [NetRingBufferIncrementIndex](../netringbuffer/nf-netringbuffer-netringbufferincrementindex.md) to advance **NextIndex**. This routine handles ring buffer wrap around.

	```C++
	VOID
	EvtRxQueueAdvance(NETRXQUEUE RxQueue)
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

			// program netPacket to hardware
			...

			// Return the packet to the available descriptor queue
			ringBuffer->NextIndex =
				NetRingBufferIncrementIndex(ringBuffer, ringBuffer->NextIndex);
		}

		// Indicate received packets (see next example)
		...
	}
	```
3. Return completed packets to the OS by incrementing **BeginIndex**. If the driver completes packets asynchronously in software (for example, a USB bus completes receive requests asynchronously), use the **Completed** flag on the packet's first [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) to track completion.

	```c++
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
			NET_PACKET_FRAGMENT* fragment = NET_PACKET_GET_FRAGMENT(netPacket, descriptor, 0);
			if (!fragment->Completed)
				break;

			ringBuffer->BeginIndex =
				NetRingBufferIncrementIndex(ringBuffer, ringBuffer->BeginIndex);
		}
	```

## -see-also

[NetRxQueueGetDatapathDescriptor](nf-netrxqueue-netrxqueuegetdatapathdescriptor.md)