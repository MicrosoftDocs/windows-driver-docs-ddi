---
UID: NF:netpacket.NetPacketGetPacketLargeSendSegmentation
title: NetPacketGetPacketLargeSendSegmentation function
author: windows-driver-content
description: The NetPacketGetPacketLargeSendSegmentation method retrieves large send offload (LSO) information for a packet.
ms.assetid: cd6668b9-37f0-4b67-a1b1-970465f894b8
ms.author: windowsdriverdev
ms.date: 03/02/2018
ms.topic: function
ms.keywords: NetPacketGetPacketLargeSendSegmentation
req.header: netpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:NtosKrnl.exe
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
-	NetPacketGetPacketLargeSendSegmentation
product: Windows
targetos: Windows

---

# NetPacketGetPacketLargeSendSegmentation function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetPacketGetPacketLargeSendSegmentation** method retrieves large send offload (LSO) information for a packet.

## -parameters

### -param packet
A pointer to the [NET_PACKET](ns-netpacket-_net_packet.md). 

### -param offset
The offset, in bytes, to the LSO [NET_PACKET_EXTENSION](../netadapterpacket/ns-netadapterpacket-_net_packet_extension.md) from the beginning of the packet's descriptor.

## -returns
Returns a pointer to a [NET_PACKET_LARGE_SEND_SEGMENTATION](ns-netpacket-_net_packet_large_send_segmentation.md) structure that holds the LSO information for this packet.

## -remarks
NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* or *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*. Clients can retrieve the offset from the queue context when they call **NetPacketGetPacketLargeSendSegmentation**.

This method is a wrapper method around [NetPacketGetExtension](nf-netpacket-netpacketgetextension.md). 

The minimum NetAdapterCx version for **NetPacketGetPacketLargeSendSegmentation** is 1.2.

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[NetPacketGetExtension](nf-netpacket-netpacketgetextension.md)