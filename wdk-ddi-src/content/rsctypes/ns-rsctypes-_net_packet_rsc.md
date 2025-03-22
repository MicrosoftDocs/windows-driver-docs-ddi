---
UID: NS:rsctypes._NET_PACKET_RSC
title: NET_PACKET_RSC (rsctypes.h)
description: The NET_PACKET_RSC structure contains receive segment coalescence (RSC) information for a packet.
tech.root: netvista
ms.date: 01/18/2024
keywords: ["NET_PACKET_RSC structure"]
ms.keywords: NET_PACKET_RSC, NET_PACKET_RSC,
req.header: rsctypes.h
req.construct-type: structure
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.33 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_PACKET_RSC
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_PACKET_RSC
 - rsctypes/_NET_PACKET_RSC
 - NET_PACKET_RSC
 - rsctypes/NET_PACKET_RSC
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - rsctypes.h
api_name:
 - _NET_PACKET_RSC
 - NET_PACKET_RSC
---

# NET_PACKET_RSC structure (rsctypes.h)




## -description

The **NET_PACKET_RSC** structure contains receive segment coalescence (RSC) information for a packet.

## -struct-fields

### -field DUMMYUNIONNAME

A union that contains the **TCP** and **UDP** members.

### -field DUMMYUNIONNAME.TCP

A structure that holds the TCP RSC information.

### -field DUMMYUNIONNAME.TCP.CoalescedSegmentCount

The number of TCP data segments that were coalesced.

### -field DUMMYUNIONNAME.TCP.DuplicateAckCount 

The number of duplicate ACK messages.

### -field DUMMYUNIONNAME.UDP

A structure that holds the UDP RSC information.

### -field DUMMYUNIONNAME.UDP.CoalescedSegmentCount

The number of UDP data segments that were coalesced.

### -field DUMMYUNIONNAME.UDP.CoalescedSegmentSize

The size, in bytes, of the UDP data segments that were coalesced.

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketRsc**](../rsc/nf-rsc-netextensiongetpacketrsc.md).

## -see-also

[Receive Segment Coalescing (RSC) offload](/windows-hardware/drivers/netcx/rsc-offload)

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

