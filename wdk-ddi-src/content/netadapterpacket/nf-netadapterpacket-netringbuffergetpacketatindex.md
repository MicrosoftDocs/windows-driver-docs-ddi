---
UID: NF:netadapterpacket.NetRingBufferGetPacketAtIndex
title: NetRingBufferGetPacketAtIndex function
author: windows-driver-content
description: Returns a pointer to the net packet at the specified index value of the packet ring buffer.
ms.assetid: 26c6887c-0805-4850-9e53-5cf22d377b3e
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetRingBufferGetPacketAtIndex
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
-	NetRingBufferGetPacketAtIndex
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRingBufferGetPacketAtIndex function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Returns a pointer to the net packet at the specified index value of the packet ring buffer.

## -parameters

### -param Descriptor
A pointer to the datapath queue's [NET_DATAPATH_DESCRIPTOR](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

### -param Index
The packet index, within the range [0, RingBuffer->NumberOfElements).

## -returns
Returns a pointer to the net packet at the specified index value of the packet ring buffer.

## -remarks
Call **NetTx(Rx)QueueGetDatapathDescriptor** to obtain the datapath descriptor structure for the queue with which you're working.

For more info, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).



## -see-also