---
UID: NF:pktmonclntk.PktMonClntNblLog
tech.root: netvista
title: PktMonClntNblLog
ms.date: 03/14/2025
targetos: Windows
description: The PktMonClntNblLog function logs that a network packet has flowed through an edge, as opposed to being dropped.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - PktMonClntNblLog
f1_keywords:
 - PktMonClntNblLog
 - pktmonclntk/PktMonClntNblLog
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - PktMonClntNblLog
---

## -description

The **PktMonClntNblLog** function logs that a network packet has flowed through an edge, as opposed to being dropped.

## -parameters

### -param EdgeContext

Pointer to the **[PKTMON_EDGE_CONTEXT](ns-pktmonclntk-pktmon_edge_context.md)** structure that holds the edge context. The *EdgeContext* parameter identifies the edge at which the action was taken.

### -param NetBufferList

Pointer to the **[NET_BUFFER_LIST](../nbl/ns-nbl-net_buffer_list.md)** structure.

### -param PacketType

The type of packet being logged. This must be one of the values defined in the **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)** enumeration.

### -param PacketHeaderInformation

Pointer to the **[PKTMON_PACKET_HEADER_INFORMATION](../pktmonnpik/ns-pktmonnpik-pktmon_packet_header_information.md)** structure containing the packet header information. Can be NULL.

### -param UseOnlyFirstNbl

When TRUE, indicates that only the first NBL in NetBufferList should be used. Otherwise, all NBLs are used.

### -param Direction

Indicates the packet direction. Each component reports packets in two directions only, IN or OUT. Must be one of the values from the **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)** enumeration.

## -remarks

## -see-also

- **[PKTMON_EDGE_CONTEXT](ns-pktmonclntk-pktmon_edge_context.md)**
- **[NET_BUFFER_LIST](../nbl/ns-nbl-net_buffer_list.md)**
- **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)**
- **[PKTMON_PACKET_HEADER_INFORMATION](../pktmonnpik/ns-pktmonnpik-pktmon_packet_header_information.md)**
- **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)**
