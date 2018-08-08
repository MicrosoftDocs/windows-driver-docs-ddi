---
UID: NF:netpacket.NetPacketGetPacketChecksum
title: NetPacketGetPacketChecksum function
author: windows-driver-content
description: The NetPacketGetPacketChecksum method retrieves checksum information for a packet.
ms.assetid: 75774f8a-eeea-4bcd-a15b-2d28a7938e42
ms.author: windowsdriverdev
ms.date: 03/02/2018
ms.topic: function
ms.keywords: NetPacketGetPacketChecksum
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
-	NetPacketGetPacketChecksum
product:
-	Windows
targetos: Windows

---

# NetPacketGetPacketChecksum function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetPacketGetPacketChecksum** method retrieves checksum information for a packet.

## -parameters

### -param packet
A pointer to the [NET_PACKET](ns-netpacket-_net_packet.md). 

### -param offset
The offset, in bytes, to the checksum [NET_PACKET_EXTENSION](../netadapterpacket/ns-netadapterpacket-_net_packet_extension.md) from the beginning of the packet's descriptor.

## -returns
Returns a pointer to a [NET_PACKET_EXTENSION](ns-netpacket-_net_packet_checksum.md) structure that holds the checksum information for this packet.

## -remarks
NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* or *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*. Clients can store checksum offset information this way and retrieve it from the queue context when they call **NetPacketGetPacketChecksum**.

This method is a wrapper method around [NetPacketGetExtension](nf-netpacket-netpacketgetextension.md). 



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[NetPacketGetExtension](nf-netpacket-netpacketgetextension.md)