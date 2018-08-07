---
UID: NS:netpacket._NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
title: _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
author: windows-driver-content
description: The NET_PACKET_RECEIVE_SEGMENT_COALESCENCE structure contains receive segment coalescence (RSC) information for a packet.
ms.assetid: 6385d38a-1731-4dc3-81db-d61bca59621e
ms.author: windowsdriverdev
ms.date: 03/02/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE, NET_PACKET_RECEIVE_SEGMENT_COALESCENCE, 
req.header: netpacket.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netpacket.h
apiname: 
-	_NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
product:
-	Windows
targetos: Windows
---

# _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE structure

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_PACKET_RECEIVE_SEGMENT_COALESCENCE** structure contains receive segment coalescence (RSC) information for a packet.

## -struct-fields

### -field DUMMYUNIONNAME
A union that contains the **TCP** member.

### -field DUMMYUNIONNAME.TCP
A structure that holds the TCP RSC information.
 
### -field DUMMYUNIONNAME.TCP.RscTcpTimestampDelta
The absolute delta between the earliest and the latest TCP timestamp value seen in the sequence of coalesced segments comprising the Single Coalesced Unit (SCU).

### -field CoalescedSegmentCount
The number of data segments that were coalesced.

## -remarks
Client drivers can obtain this structure for a packet by calling [NetPacketGetPacketReceiveSegmentCoalescence](nf-netpacket-netpacketgetpacketreceivesegmentcoalescence.md).



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)