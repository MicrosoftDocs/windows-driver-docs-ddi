---
UID: NS:pktmonclntnpik._PKTMON_PACKET_LOG_IN
tech.root: netvista
title: PKTMON_PACKET_LOG_IN
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PACKET_LOG_IN structure contains information about a packet being logged for monitoring purposes.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_PACKET_LOG_IN
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntnpik.h
api_name:
 - _PKTMON_PACKET_LOG_IN
 - PKTMON_PACKET_LOG_IN
f1_keywords:
 - _PKTMON_PACKET_LOG_IN
 - pktmonclntnpik/_PKTMON_PACKET_LOG_IN
 - PKTMON_PACKET_LOG_IN
 - pktmonclntnpik/PKTMON_PACKET_LOG_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PACKET_LOG_IN
---

## -description

The **PKTMON_PACKET_LOG_IN** structure contains information about a packet being logged for monitoring purposes. This structure is passed to both packet log and packet drop callbacks to provide packet metadata.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header) structure used for versioning and size validation.

### -field Buffer

A pointer to the packet buffer. The interpretation of this pointer depends on the `BufferType` field.

### -field BufferType

A **[PKTMON_BUFFER_TYPE](ne-pktmonclntnpik-pktmon_buffer_type.md)** enumeration value that specifies the format of the packet buffer (e.g., NBL chain, single NBL, WSK buffer, or none).

### -field PacketType

A **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)** enumeration value that indicates the type of packet being logged (e.g., Ethernet, IP, etc.).

### -field Direction

A **[PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)** enumeration value that specifies whether the packet is inbound or outbound relative to the monitoring edge.

### -field Flags

Flags providing additional information about the packet logging operation. The specific flags are defined by the implementation.

### -field PacketHeaderInfo

An optional pointer to a **[PKTMON_PACKET_HEADER_INFO](ns-pktmonclntnpik-pktmon_packet_header_info.md)** structure containing parsed packet header information. Can be NULL if header information is not available.

## -remarks

This structure is used by both **[PKTMON_PROVIDER_PACKET_LOG](nc-pktmonclntnpik-pktmon_provider_packet_log.md)** and **[PKTMON_PROVIDER_PACKET_DROP](nc-pktmonclntnpik-pktmon_provider_packet_drop.md)** callbacks.

## -see-also

- [PKTMON_PROVIDER_PACKET_LOG](nc-pktmonclntnpik-pktmon_provider_packet_log.md)
- [PKTMON_PROVIDER_PACKET_DROP](nc-pktmonclntnpik-pktmon_provider_packet_drop.md)
- [PKTMON_BUFFER_TYPE](ne-pktmonclntnpik-pktmon_buffer_type.md)

