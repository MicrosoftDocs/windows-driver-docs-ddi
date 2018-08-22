---
UID: NF:netadapterpacket.NetRingBufferGetNextPacket
title: NetRingBufferGetNextPacket function
author: windows-driver-content
description: Returns a pointer to the packet in a packet ring buffer at the ring buffer's NextIndex index value.
ms.assetid: f77fdf7a-cd55-4828-9eeb-1853dae6a023
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetRingBufferGetNextPacket
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
-	NetRingBufferGetNextPacket
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetRingBufferGetNextPacket function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Returns a pointer to the packet in a packet ring buffer at the ring buffer's **NextIndex** index value.

## -parameters

### -param Descriptor
A pointer to the datapath queue's [NET_DATAPATH_DESCRIPTOR](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

## -returns
Returns **NULL** if the ring buffer's **NextIndex** equals its **EndIndex**, meaning there are no more unprocessed packets. Otherwise, this routine returns a pointer to the [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) at the new **NextIndex** value of the ring buffer.

## -remarks
Call **NetTx(Rx)QueueGetDatapathDescriptor** to obtain the datapath descriptor structure for the queue with which you're working.

This routine is similar to [NetRingBufferAdvanceNextPacket](nf-netadapterpacket-netringbufferadvancenextpacket.md). The difference is that this routine does not modify the packet ring buffer's **NextIndex** field; the ring buffer is not modified.

Typically, your driver would use **NetRingBufferGetNextPacket** to get the next packet to program into hardware. Because **NetRingBufferGetNextPacket** does not increment **NextIndex**, you'll also eventually need to increment the index. For example:

```c++
NET_PACKET *nextPacket;
while (NULL != (nextPacket = NetRingBufferGetNextPacket(descriptor))) {
  if (!EnoughMemoryAvailableForPacket(nextPacket))
    break;

    ProgramPacketToMyHardware(nextPacket);
    NetRingBufferAdvanceNextPacket(descriptor);
}
```

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).



## -see-also