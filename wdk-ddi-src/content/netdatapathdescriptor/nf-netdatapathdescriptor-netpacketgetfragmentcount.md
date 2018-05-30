---
UID: NF:netdatapathdescriptor.NetPacketGetFragmentCount
title: NetPacketGetFragmentCount function
author: windows-driver-content
description: The NetPacketGetFragmentCount method obtains the total number of fragments in a net packet.
ms.assetid: 7d4b623d-c114-4800-a4e2-d63c3bb399e0
ms.author: windowsdriverdev
ms.date: 02/27/2018
ms.topic: function
ms.keywords: NetPacketGetFragmentCount
req.header: netdatapathdescriptor.h
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
-	NetPacketGetFragmentCount
product: Windows
targetos: Windows

---

# NetPacketGetFragmentCount function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The NetPacketGetFragmentCount method obtains the total number of fragments in a net packet.

## -parameters

### -param Descriptor
A pointer to the datapath queue's [NET_DATAPATH_DESCRIPTOR](ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

### -param Packet
A pointer to a [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) structure.

## -returns
Returns the total number of [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md)s in the [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md).

## -remarks
This method can be called to first obtain the number of fragments in a packet before looping over all the fragments. For a code example that uses this method, see [NET_PACKET_GET_FRAGMENT](nf-netdatapathdescriptor-net_packet_get_fragment.md).



## -see-also

[Packet descriptors and extensiosn](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)