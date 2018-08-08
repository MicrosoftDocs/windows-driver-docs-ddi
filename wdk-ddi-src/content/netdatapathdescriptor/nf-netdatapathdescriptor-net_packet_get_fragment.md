---
UID: NF:netdatapathdescriptor.NET_PACKET_GET_FRAGMENT
title: NET_PACKET_GET_FRAGMENT macro
author: windows-driver-content
description: The NET_PACKET_GET_FRAGMENT macro retrieves a single fragment from a net packet.
ms.assetid: ee42c2b6-078c-493e-8b47-67aecffc7be7
ms.author: windowsdriverdev
ms.date: 02/27/2018
ms.topic: macro
ms.keywords: NET_PACKET_GET_FRAGMENT
req.header: netdatapathdescriptor.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: netdatapathdescriptor.h
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
-	HeaderDef
apilocation: 
-	netdatapathdescriptor.h
apiname: 
-	NET_PACKET_GET_FRAGMENT
product:
-	Windows
targetos: Windows

---

# NET_PACKET_GET_FRAGMENT macro


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_PACKET_GET_FRAGMENT** macro retrieves a single fragment from a net packet.

## -parameters

### -param packet
A pointer to the [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) to which the fragment belongs.

### -param desc
A pointer to the datapath queue's [NET_DATAPATH_DESCRIPTOR](ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

### -param index
The index of the fragment in the datapath queue's fragment ring buffer, relative to the parent packet.

## -remarks
[NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md)s are organized in a ring buffer just like [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md)s. Each packet in the packet ring buffer references the start of its fragments in the fragment ring buffer. Because fragments are contained within a packet, this means that the *index* parameter of this macro is the index of the fragment *within* the packet and not in the overall fragment ring buffer. 

For example, consider a NIC driver that wants to check information about an Ethernet frame on its transmit queue. The driver can use the 0th index of the packet and call **NET_PACKET_GET_FRAGMENT** to check the first fragment and make sure the Ethernet header is there, then it can get the number of fragments with a call to [NetPacketGetFragmentCount](nf-netdatapathdescriptor-netpacketgetfragmentcount.md) and loop over the fragments, calling **NET_PACKET_GET_FRAGMENT** on each one, to find out the total data length. To obtain this information, the example first acquires the queue's datapath descriptor by calling [NetTxQueueGetDatapathDescriptor](../nettxqueue/nf-nettxqueue-nettxqueuegetdatapathdescriptor.md).

```C++

// Get the Tx queue's datapath descriptor
PCNET_DATAPATH_DESCRIPTOR descriptor = NetTxQueueGetDatapathDescriptor(txQueue);

// Verify the first fragment has the Ethernet header
NET_PACKET_FRAGMENT* fragment = NET_PACKET_GET_FRAGMENT(packet, descriptor, 0);
if(fragment->ValidLength < sizeof(ETHERNET_HEADER))
{
    return;
}

// Obtain the total length of the fragments in this packet
UINT32 fragmentCount = NetPacketGetFragmentCount(descriptor, packet);
ULONG dataLength = 0;
for(UINT32 i = 0; i < fragmentCount; i++)
{
    fragment = NET_PACKET_GET_FRAGMENT(packet, descriptor, i);
    dataLength += (ULONG)fragment->ValidLength;

    if(fragment->LastFragmentOfFrame)
    {
        break;
    }
}

```



## -see-also

[Packet descriptors and extensiosn](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)