---
UID: NS:ieee8021qtypes._NET_PACKET_IEEE8021Q
tech.root: netvista
title: NET_PACKET_IEEE8021Q
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: The NET_PACKET_IEEE8021Q structure specifies a NET_PACKET's 802.1Q information.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ieee8021qtypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: NET_PACKET_IEEE8021Q
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ieee8021qtypes.h
api_name:
 - _NET_PACKET_IEEE8021Q
 - NET_PACKET_IEEE8021Q
f1_keywords:
 - _NET_PACKET_IEEE8021Q
 - ieee8021qtypes/_NET_PACKET_IEEE8021Q
 - NET_PACKET_IEEE8021Q
 - ieee8021qtypes/NET_PACKET_IEEE8021Q
dev_langs:
 - c++
---

## -description

The **NET_PACKET_IEEE8021Q** structure describes the IEEE 802.1Q information for a [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -struct-fields

### -field PriorityCodePoint

Specifies the 802.1p priority information that is used to establish packet priority in shared-media 802 networks. The bits in this member specify an 802.1p priority value.

### -field VlanIdentifier

Identifies the virtual LAN (VLAN) that a packet belongs to.

### -field TxTagging

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketIeee8021Q**](../ieee8021q/nf-ieee8021q-netextensiongetpacketieee8021q.md).

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetPacketIeee8021Q**](../ieee8021q/nf-ieee8021q-netextensiongetpacketieee8021q.md)

