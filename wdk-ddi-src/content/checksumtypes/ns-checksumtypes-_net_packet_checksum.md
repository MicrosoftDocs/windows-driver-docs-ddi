---
UID: NS:checksumtypes._NET_PACKET_CHECKSUM
title: _NET_PACKET_CHECKSUM (checksumtypes.h)
description: A NET_PACKET_CHECKSUM structure describes checksum information for a NET_PACKET.
tech.root: netvista
ms.assetid: 75363870-C58D-4677-A523-9728CB4A1BAC
ms.date: 09/25/2019
keywords: ["_NET_PACKET_CHECKSUM structure"]
f1_keywords:
 - "checksumtypes/BATTERY_INFORMATION"
ms.keywords: _NET_PACKET_CHECKSUM, NET_PACKET_CHECKSUM, *PNET_PACKET_CHECKSUM
req.header: checksumtypes.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_PACKET_CHECKSUM
topictype:
- APIRef
apitype: 
- HeaderDef
apilocation: 
- checksumtypes.h
apiname: 
- NET_PACKET_CHECKSUM
targetos: Windows
product:
- Windows
---

# _NET_PACKET_CHECKSUM structure

## -description

A **NET_PACKET_CHECKSUM** structure describes checksum information for a [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -struct-fields

### -field Layer2

A bit field that specifies a flag from either [**NET_PACKET_TX_CHECKSUM_ACTION**](../checksumtypes/ne-checksumtypes-_net_packet_tx_checksum_action.md) or [**NET_PACKET_RX_CHECKSUM_EVALUATION**](../checksumtypes/ne-checksumtypes-_net_packet_rx_checksum_evaluation.md). Targets the checksum field in the packet's layer 2 header.

### -field Layer3

A bit field that specifies a flag from either [**NET_PACKET_TX_CHECKSUM_ACTION**](../checksumtypes/ne-checksumtypes-_net_packet_tx_checksum_action.md) or [**NET_PACKET_RX_CHECKSUM_EVALUATION**](../checksumtypes/ne-checksumtypes-_net_packet_rx_checksum_evaluation.md). Targets the checksum field in the packet's layer 3 header.

### -field Layer4

A bit field that specifies a flag from either [**NET_PACKET_TX_CHECKSUM_ACTION**](../checksumtypes/ne-checksumtypes-_net_packet_tx_checksum_action.md) or [**NET_PACKET_RX_CHECKSUM_EVALUATION**](../checksumtypes/ne-checksumtypes-_net_packet_rx_checksum_evaluation.md). Targets the checksum field in the packet's layer 4 header.

### -field Reserved

Reserved for system use.

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketChecksum**](../checksum/nf-checksum-netextensiongetpacketchecksum.md).

For a transmit queue, the client specifies flag values from the [**NET_PACKET_TX_CHECKSUM_ACTION**](../checksumtypes/ne-checksumtypes-_net_packet_tx_checksum_action.md) enumeration. In a transmit queue, the client cross-references the **Checksum** information for a packet with the [**Layout**](../packet/ns-packet-_net_packet_layout.md) member of a [**NET_PACKET**](../packet/ns-packet-_net_packet.md) in order to determine which hardware transmit checksum offloads need to be enabled.

For a receive queue, the client specifies flag values from the [**NET_PACKET_RX_CHECKSUM_EVALUATION**](../checksumtypes/ne-checksumtypes-_net_packet_rx_checksum_evaluation.md) enumeration. The client should also fill out the [**Layout**](../packet/ns-packet-_net_packet_layout.md) member of the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure.

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
