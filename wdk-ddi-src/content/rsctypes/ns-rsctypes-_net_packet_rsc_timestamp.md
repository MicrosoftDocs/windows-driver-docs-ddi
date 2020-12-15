---
UID: NS:rsctypes._NET_PACKET_RSC_TIMESTAMP
title: NET_PACKET_RSC_TIMESTAMP (rsctypes.h)
description: The NET_PACKET_RSC_TIMESTAMP structure contains receive segment coalescence (RSC) timestamp information for a packet.
tech.root: netvista
ms.date: 09/24/2019
keywords: ["NET_PACKET_RSC_TIMESTAMP structure"]
ms.keywords: NET_PACKET_RSC_TIMESTAMP, NET_PACKET_RSC_TIMESTAMP,
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
req.typenames: NET_PACKET_RSC_TIMESTAMP
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_PACKET_RSC_TIMESTAMP
 - rsctypes/_NET_PACKET_RSC_TIMESTAMP
 - NET_PACKET_RSC_TIMESTAMP
 - rsctypes/NET_PACKET_RSC_TIMESTAMP
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - rsctypes.h
api_name:
 - NET_PACKET_RSC_TIMESTAMP
product:
 - Windows
---

# NET_PACKET_RSC_TIMESTAMP structure


## -description

The **NET_PACKET_RSC_TIMESTAMP** structure contains receive segment coalescence (RSC) timestamp information for a packet.

## -struct-fields

### -field DUMMYUNIONNAME

A union that contains the **TCP** member.

### -field DUMMYUNIONNAME.TCP

A structure that holds the TCP RSC timestamp information.

### -field DUMMYUNIONNAME.TCP.RscTcpTimestampDelta

 
The absolute delta between the earliest and the latest TCP timestamp value seen in the sequence of coalesced segments comprising the Single Coalesced Unit (SCU).

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketRscTimeStamp**](../rsc/nf-rsc-netextensiongetpacketrsctimestamp.md).

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
