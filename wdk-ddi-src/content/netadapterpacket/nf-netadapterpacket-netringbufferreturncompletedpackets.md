---
UID: NF:netadapterpacket.NetRingBufferReturnCompletedPackets
title: NetRingBufferReturnCompletedPackets function
author: windows-driver-content
description: Returns all packets that have the Completed flag set.
ms.assetid: 3699e976-e007-42f8-9785-9f13d0d56c57
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetRingBufferReturnCompletedPackets
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
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
-	HeaderDef
apilocation: 
-	netadapterpacket.h
apiname: 
-	NetRingBufferReturnCompletedPackets
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRingBufferReturnCompletedPackets function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Returns all packets that have the **Completed** flag set.

## -parameters

### -param RingBuffer
A pointer to a [NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md).

## -returns
This method does not return a value.

## -remarks
The NetAdapter data path requires packets to be completed in the order that they are given to your driver. If your driver can complete some packets out of order, you can use **NetRingBufferReturnCompletedPackets** to simplify your completion path.

To use this convenience function, first set the **Completed** flag on the first fragment of all packets with which your driver is finished, whether the packets were processed successfully or not. Then, call **NetRingBufferReturnCompletedPackets** to batch the completion of all consecutive packets for which the first fragment has the **Completed** flag set.

**NetRingBufferReturnCompletedPackets** completes packets by writing a new value to the **BeginIndex** of the ring buffer.

If you always complete packets in order, it is more efficient to write to **BeginIndex** directly, rather than using the **Completed** flag with **NetRingBufferReturnCompletedPackets**.

When you use **NetRingBufferReturnCompletedPackets**, it is most efficient to flag all finished packets and call the routine just once.

The minimum NetAdapterCx version for **NetRingBufferReturnCompletedPackets** is 1.0.

### Example

This example shows how a simple data path can complete packets if the hardware completes I/O requests in the order in which they were issued. Note that this data path just writes to **eginIndex** directly.

```c++
for (UINT i = ringBuffer->BeginIndex; 
     i != ringBuffer->EndIndex; 
     i = NetRingBufferIncrementIndex(ringBuffer, i))
{
  NET_PACKET *packet = NetRingBufferGetPacketAtIndex(ringBuffer, i);
  if (!MyHardwareIsDoneWithPacket(packet))
    break;

  // Complete the packet to the OS, simply by updating BeginIndex
  ringBuffer->BeginIndex = i;
}
```

But suppose that your hardware or lower edge completes packets out of order. Now you cannot just assign the index of the most recently completed packet to **BeginIndex**. Instead, use the **Completed** flag with **NetRingBufferReturnCompletedPackets** to return packets safely.

In this example, the lower edge returns a linked list of I/O completion blocks, and the list is not sorted in the order in which the I/O requests were issued.

```c++
void MyPacketCompletionCallback(MY_IO_REQUEST *io)
{
  while (io) {
    NET_PACKET *packet = io->Packet;
    packet->Data.Completed = TRUE;

    // Walk the linked list
    io = io->Next;
  }

  // Complete any packets to the OS.  Updates BeginIndex for us.
  NetRingBufferReturnCompletedPackets(ringBuffer);
}
```
For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

## -see-also