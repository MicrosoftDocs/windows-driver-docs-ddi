---
UID: NF:netadapterpacket.NetRingBufferReturnAllPackets
title: NetRingBufferReturnAllPackets function
description: The NetRingBufferReturnAllPackets method returns all packets in a datapath queue's packet ring buffer.
tech.root: netvista
ms.assetid: f4d7932d-0e28-4583-a505-aba889f8be27
ms.date: 02/28/2018
ms.topic: function
ms.keywords: NetRingBufferReturnAllPackets
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetRingBufferReturnAllPackets
product:
-	Windows
targetos: Windows

---

# NetRingBufferReturnAllPackets function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The NetRingBufferReturnAllPackets method returns all packets in a datapath queue's packet ring buffer.

## -parameters

### -param Descriptor
A pointer to the datapath queue's [NET_DATAPATH_DESCRIPTOR](../netdatapathdescriptor/ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

## -returns
This method does not return a value.

## -remarks
Call **NetTx(Rx)QueueGetDatapathDescriptor** to obtain the datapath descriptor structure for the queue with which you're working.

This method is a convenience function to return all outstanding packets. Typically, you would call this method from your [*EvtPacketQueueCancel*](../netpacketqueue/nc-netpacketqueue-evt_packet_queue_cancel.md) callback function for a receive queue.



## -see-also
