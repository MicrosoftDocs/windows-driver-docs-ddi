---
UID: NF:netadapterpacket.NetRingBufferAdvanceNextPacket
title: NetRingBufferAdvanceNextPacket function
author: windows-driver-content
description: Increments the NextIndex value of the ring buffer, then returns a pointer to the packet at the new NextIndex value.
ms.assetid: 0b83570a-5d36-4ddd-8289-1506304990b7
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetRingBufferAdvanceNextPacket
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
-	NetRingBufferAdvanceNextPacket
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRingBufferAdvanceNextPacket function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Increments the NextIndex value of the ring buffer, then returns a pointer to the packet at the new NextIndex value.

## -parameters

### -param RingBuffer
A pointer to a [NET_RING_BUFFER](../netringbuffer/ns-netringbuffer-_net_ring_buffer.md).

## -returns
Returns **NULL** if the ring buffer's **NextIndex** equals its **EndIndex**, meaning there are no more unprocessed packets. Otherwise, this routine returns a pointer to the [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) at the new **NextIndex** value of the ring buffer.

## -remarks
Typically, your driver would use NetRingBufferAdvanceNextPacket in a loop to issue packets to hardware.

For example:

```c++
NET_PACKET *nextPacket;
while (NULL != (nextPacket = NetRingBufferAdvanceNextPacket(ringBuffer))) {
  ProgramPacketToMyHardware(nextPacket);
}
```

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).

The minimum NetAdapterCx version for **NetRingBufferAdvanceNextPacket** is 1.0.

## -see-also