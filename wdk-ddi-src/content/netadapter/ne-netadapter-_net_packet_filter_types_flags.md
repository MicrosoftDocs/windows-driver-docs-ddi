---
UID: NE:netadapter._NET_PACKET_FILTER_TYPES_FLAGS
title: _NET_PACKET_FILTER_TYPES_FLAGS
author: windows-driver-content
description: Specifies packet filters that control the types of packets the NIC completes on its receive path.
tech.root: netvista
ms.assetid: a701a508-aaf8-4272-bdb5-d5d57b33ae08
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: enum
ms.keywords: _NET_PACKET_FILTER_TYPES_FLAGS, NET_PACKET_FILTER_TYPES_FLAGS, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_PACKET_FILTER_TYPES_FLAGS
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_PACKET_FILTER_TYPES_FLAGS
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_PACKET_FILTER_TYPES_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Specifies packet filters that control the types of packets the NIC completes on its receive path.

## -enum-fields

### -field NET_PACKET_FILTER_TYPE_DIRECTED : 
The NIC should receive directed packets that contain a destination address equal to the station address of the NIC.

### -field NET_PACKET_FILTER_TYPE_MULTICAST : 
Multicast address packets contain a destination address equal to one of the addresses in the multicast address list.

### -field NET_PACKET_FILTER_TYPE_ALL_MULTICAST : 
All multicast address packets, not just the ones enumerated in the multicast address list.

### -field NET_PACKET_FILTER_TYPE_BROADCAST : 
Broadcast packets.

### -field NET_PACKET_FILTER_TYPE_SOURCE_ROUTING : 
All source routing packets. If the protocol driver sets this bit, the NDIS library attempts to act as a source routing bridge.

### -field NET_PACKET_FILTER_TYPE_PROMISCUOUS : 
Specifies all packets regardless of whether VLAN filtering is enabled or not and whether the VLAN identifier matches or not.

### -field NET_PACKET_FILTER_TYPE_ALL_LOCAL : 
All packets sent by installed protocols and all packets indicated by the NIC that is identified by a given *NdisBindingHandle*.

### -field NET_PACKET_FILTER_TYPE_MAC_FRAME : 
NIC driver frames that a Token Ring NIC receives.

### -field NET_PACKET_FILTER_TYPE_NO_LOCAL : 
No local packets. This prevents looping back of packets. For more info, see [Looping Back NDIS Packets](https://docs.microsoft.com/windows-hardware/drivers/network/looping-back-ndis-packets).

## -remarks

The **NET_PACKET_FILTER_TYPES_FLAGS** enumeration is used to specify supported packet filters in the [NET_ADAPTER_LINK_LAYER_CAPABILITIES](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure.

The client driver passes an initialized **NET_ADAPTER_LINK_LAYER_CAPABILITIES** structure as an input parameter value to [NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md).

For info about the data path, see [Transferring Network Data](https://docs.microsoft.com/windows-hardware/drivers/netcx/transferring-network-data).



## -see-also

NET_ADAPTER_LINK_LAYER_CAPABILITIES

[OID_GEN_CURRENT_PACKET_FILTER](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter)
