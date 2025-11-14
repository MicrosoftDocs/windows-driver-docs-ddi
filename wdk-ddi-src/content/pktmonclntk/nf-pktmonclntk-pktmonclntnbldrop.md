---
UID: NF:pktmonclntk.PktMonClntNblDrop
tech.root: netvista
title: PktMonClntNblDrop
ms.date: 04/04/2025
targetos: Windows
description: The PktMonClntNblDrop function logs that a network packet was dropped.
ai-usage: ai-assisted
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
 - PktMonClntNblDrop
f1_keywords:
 - PktMonClntNblDrop
 - pktmonclntk/PktMonClntNblDrop
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - PktMonClntNblDrop
---

## -description

The **PktMonClntNblDrop** function logs that a network packet was dropped. Additional information can be provided about why and where it got dropped.

## -parameters

### -param CompContext

Pointer to **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** which holds the context for the component.

### -param NetBufferList

Pointer to the **[NET_BUFFER_LIST](../nbl/ns-nbl-net_buffer_list.md)** structure.

### -param PacketType

The type of packet being logged. This must be one of the values defined in the **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)** enumeration.

### -param PacketHeaderInformation

Pointer to the **[PKTMON_PACKET_HEADER_INFORMATION](../pktmonclntk/ns-pktmonclntk-pktmon_packet_header_information.md)** structure containing the packet header information. Can be NULL.

### -param UseOnlyFirstNbl

When TRUE, indicates that only the first NBL in NetBufferList was dropped. Otherwise, all NBLs were dropped.

### -param Direction

Indicates the packet direction. Each component reports packets in two directions only, IN or OUT. Must be one of the values from the **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)** enumeration.

### -param DropReason

Integer that indicates the reason for the packet to be dropped.

| Value | Usage |
|--|--|
| 0 - 0x7FFFFFFF | Reserved for Microsoft. |
| 0x80000000 - 0xFFFFFFFF | Free to be used. |

### -param LocationCode

Integer that indicates the location where the packet got dropped.

| Value | Usage |
|--|--|
| 0 - 0x7FFFFFFF | Free to be used. |
| 0x80000000 - 0xFFFFFFFF | Reserved for Microsoft. |

## -remarks

## -see-also

- **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)**
- **[NET_BUFFER_LIST](../nbl/ns-nbl-net_buffer_list.md)**
- **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)**
- **[PKTMON_PACKET_HEADER_INFORMATION](ns-pktmonclntk-pktmon_packet_header_information.md)**
- **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)**
