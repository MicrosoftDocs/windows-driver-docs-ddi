---
UID: NS:rsctypes._NET_PACKET_RSC
title: NET_PACKET_RSC (rsctypes.h)
author: windows-driver-content
description: The NET_PACKET_RSC structure contains receive segment coalescence (RSC) information for a packet.
tech.root: netvista
ms.assetid: fda0e3e5-cb78-480c-a885-14d412755af9
ms.author: windowsdriverdev
ms.date: 09/24/2019
keywords: ["NET_PACKET_RSC structure"]
ms.keywords: NET_PACKET_RSC, NET_PACKET_RSC,
req.header: rsctypes.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
 - NET_PACKET_RSC
product:
 - Windows
---

# NET_PACKET_RSC structure


## -description

The **NET_PACKET_RSC** structure contains receive segment coalescence (RSC) information for a packet.

## -struct-fields

### -field DUMMYUNIONNAME

A union that contains the **TCP** member.

### -field DUMMYUNIONNAME.TCP

A structure that holds the TCP RSC information.

### -field DUMMYUNIONNAME.TCP.CoalescedSegmentCount

The number of data segments that were coalesced.

### -field DUMMYUNIONNAME.TCP.DuplicateAckCount 

The number of duplicate ACK messages.

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketRsc**](../rsc/nf-rsc-netextensiongetpacketrsc.md).

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)