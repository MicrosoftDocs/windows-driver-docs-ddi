---
UID: NF:pktmonclntk.PktMonClntHeaderInfoDrop
tech.root: netvista
title: PktMonClntHeaderInfoDrop
ms.date: 03/14/2025
targetos: Windows
description: The PktMonClntHeaderInfoDrop function logs that a network packet was dropped.
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
 - PktMonClntHeaderInfoDrop
f1_keywords:
 - PktMonClntHeaderInfoDrop
 - pktmonclntk/PktMonClntHeaderInfoDrop
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - PktMonClntHeaderInfoDrop
---

## -description

The **PktMonClntHeaderInfoDrop** function logs that a network packet was dropped.

## -parameters

### -param CompContext

Pointer to the **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** structure that holds the context for the component.

### -param PacketType

The type of packet being logged. This must be one of the values defined in the **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)** enumeration.

### -param PacketHeaderInformation

Pointer to a **[PKTMON_PACKET_HEADER_INFORMATION](../pktmonnpik/ns-pktmonnpik-pktmon_packet_header_information.md)** structure containing the packet header information.

### -param Direction

Indicates the packet direction. Each component reports packets in two directions only, IN or OUT. Must be one of the values from **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)** enumeration.

### -param DropReason

Integer that indicates the reason for the packet to be dropped.

### -param LocationCode

Integer that indicates the location where the packet was dropped.

### -param Context

Pointer to a **[PKTMON_PACKET_CONTEXT_IN](../pktmonnpik/ns-pktmonnpik-pktmon_packet_context_in.md)** structure containing the packet context. Can be NULL.

## -remarks

## -see-also

- **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)**
- **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)**
- **[PKTMON_PACKET_HEADER_INFORMATION](../pktmonnpik/ns-pktmonnpik-pktmon_packet_header_information.md)**
- **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)**
- **[PKTMON_PACKET_CONTEXT_IN](../pktmonnpik/ns-pktmonnpik-pktmon_packet_context_in.md)**
