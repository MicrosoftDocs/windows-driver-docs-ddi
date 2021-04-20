---
UID: NF:ieee8021q.NetExtensionGetPacketIeee8021Q
tech.root: netvista 
title: NetExtensionGetPacketIeee8021Q
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: The NetExtensionGetPacketIeee8021Q function retrieves the 802.1Q information for a NET_PACKET.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ieee8021q.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ieee8021q.h
api_name:
 - NetExtensionGetPacketIeee8021Q
f1_keywords:
 - NetExtensionGetPacketIeee8021Q
 - ieee8021q/NetExtensionGetPacketIeee8021Q
dev_langs:
 - c++
---

## -description

The **NetExtensionGetPacketIeee8021Q** function retrieves the IEEE 802.1Q information for a [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the 802.1Q extension information for this packet queue.

### -param Index

The index in the packet ring for the target [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -returns

Returns a pointer to a [**NET_PACKET_IEEE8021Q**](../ieee8021qtypes/ns-ieee8021qtypes-net_packet_ieee8021q.md) structure that holds the 802.1Q information for this packet.

## -remarks

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_PACKET_IEEE8021Q**](../ieee8021qtypes/ns-ieee8021qtypes-net_packet_ieee8021q.md)