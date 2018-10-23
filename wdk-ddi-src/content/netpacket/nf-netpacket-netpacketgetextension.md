---
UID: NF:netpacket.NetPacketGetExtension
title: NetPacketGetExtension function
author: windows-driver-content
description: The NetPacketGetExtension method retrieves information stored in one of a packet's extensions.
tech.root: netvista
ms.assetid: 209d7b54-a5f0-435f-84c6-3ba7ac0dec53
ms.date: 03/02/2018
ms.topic: function
ms.keywords: NetPacketGetExtension
req.header: netpacket.h
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
-	NetPacketGetExtension
product:
-	Windows
targetos: Windows

---

# NetPacketGetExtension function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetPacketGetExtension** method retrieves information stored in one of a packet's extensions.

## -parameters

### -param packet
A pointer to the [NET_PACKET](ns-netpacket-_net_packet.md). 

### -param offset
The offset, in bytes, to the desired [NET_PACKET_EXTENSION](../netadapterpacket/ns-netadapterpacket-_net_packet_extension.md) from the beginning of the packet's descriptor.

## -returns
Returns a pointer to a structure at the given extension offset that represents packet extension information.

## -remarks
NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* or *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*. These offsets are then passed to **NetPacketGetExtension** to retrieve data for each packet extension.

NetAdapterCx provides several convenient wrapper methods around **NetPacketGetExtension** for offloads such as checksum, large send segmentation, and receive segment coalescence. Each of these methods returns a pointer to the appropriate structure type.

| Method | Structure |
| --- | --- |
| [NetPacketGetPacketChecksum](nf-netpacket-netpacketgetpacketchecksum.md) | [NET_PACKET_CHECKSUM](ns-netpacket-_net_packet_checksum.md) |
| [NetPacketGetPacketLargeSendSegmentation](nf-netpacket-netpacketgetpacketlargesendsegmentation.md) | [NET_PACKET_LARGE_SEND_SEGMENTATION](ns-netpacket-_net_packet_large_send_segmentation.md)
| [NetPacketGetPacketReceiveSegmentCoalescence](nf-netpacket-netpacketgetpacketreceivesegmentcoalescence.md) | [NET_PACKET_RECEIVE_SEGMENT_COALESCENCE](ns-netpacket-_net_packet_receive_segment_coalescence.md) |



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
