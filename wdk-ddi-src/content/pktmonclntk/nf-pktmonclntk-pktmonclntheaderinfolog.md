---
UID: NF:pktmonclntk.PktMonClntHeaderInfoLog
tech.root: netvista
title: PktMonClntHeaderInfoLog
ms.date: 03/14/2025
targetos: Windows
description: The PktMonClntHeaderInfoLog function logs that a network packet has flowed through, as opposed to being dropped.
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
 - PktMonClntHeaderInfoLog
f1_keywords:
 - PktMonClntHeaderInfoLog
 - pktmonclntk/PktMonClntHeaderInfoLog
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - PktMonClntHeaderInfoLog
---

## -description

The **PktMonClntHeaderInfoLog** function logs that a network packet has flowed through, as opposed to being dropped.

## -parameters

### -param EdgeContext

Pointer to a **[PKTMON_EDGE_CONTEXT](ns-pktmonclntk-pktmon_edge_context.md)** structure which holds the edge context.

### -param PacketHeaderInformation

Pointer to a **[PKTMON_PACKET_HEADER_INFORMATION](../pktmonnpik/ns-pktmonnpik-pktmon_packet_header_information.md)** structure containing the packet header information.

### -param Direction

Indicates the packet direction. Each component reports packets in two directions only, IN or OUT. Must be one of the values from **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)** enumeration.

### -param Context

Pointer to a **[PKTMON_PACKET_CONTEXT_IN](../pktmonnpik/ns-pktmonnpik-pktmon_packet_context_in.md)** structure containing the packet context, which can represent a piece of data that is meaningful to the component, like a connection ID for example. Can be NULL.

## -remarks

Like **[PktMonClntNblLog](nf-pktmonclntk-pktmonclntnbllog.md)**, **PktMonClntHeaderInfoLog** is also used for packet logging but does not require NBLs. **PktMonClntHeaderInfoLog** is useful when packet metadata needs to be logged.

## -see-also

