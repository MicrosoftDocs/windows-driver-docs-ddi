---
UID: NS:rsctypes._NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
title: _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE (rsctypes.h)
description: The NET_PACKET_RECEIVE_SEGMENT_COALESCENCE structure contains receive segment coalescence (RSC) information for a packet.
tech.root: netvista
ms.assetid: 6385d38a-1731-4dc3-81db-d61bca59621e
ms.date: 01/30/2019
ms.topic: struct
f1_keywords:
 - "rsctypes/RILWRITEPHONEBOOKENTRYPARAMS"
ms.keywords: _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE, NET_PACKET_RECEIVE_SEGMENT_COALESCENCE, 
req.header: rsctypes.h
req.include-header: netadaptercx.h
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
req.typenames: NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- rsctypes.h
apiname: 
- _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE
product:
- Windows
targetos: Windows
---

# _NET_PACKET_RECEIVE_SEGMENT_COALESCENCE structure

## -description


The **NET_PACKET_RECEIVE_SEGMENT_COALESCENCE** structure contains receive segment coalescence (RSC) information for a packet.

## -struct-fields

### -field CoalescedSegmentCount

The number of data segments that were coalesced.

### -field DUMMYUNIONNAME

A union that contains the **TCP** member.

### -field DUMMYUNIONNAME.TCP

A structure that holds the TCP RSC information.
 
### -field DUMMYUNIONNAME.TCP.RscTcpTimestampDelta

The absolute delta between the earliest and the latest TCP timestamp value seen in the sequence of coalesced segments comprising the Single Coalesced Unit (SCU).

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketReceiveSegmentCoalescence**](../rsc/nf-rsc-netextensiongetpacketreceivesegmentcoalescence.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
