---
UID: NS:pktmonnpik._PKTMON_EVT_STREAM_PACKET_HEADER
tech.root: netvista
title: PKTMON_EVT_STREAM_PACKET_HEADER
ms.date: 03/14/2025
targetos: Windows
description: The PKTMON_EVT_STREAM_PACKET_HEADER structure contains a packet header used for event streaming.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_EVT_STREAM_PACKET_HEADER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnpik.h
api_name:
 - _PKTMON_EVT_STREAM_PACKET_HEADER
 - PKTMON_EVT_STREAM_PACKET_HEADER
f1_keywords:
 - _PKTMON_EVT_STREAM_PACKET_HEADER
 - pktmonnpik/_PKTMON_EVT_STREAM_PACKET_HEADER
 - PKTMON_EVT_STREAM_PACKET_HEADER
 - pktmonnpik/PKTMON_EVT_STREAM_PACKET_HEADER
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_EVT_STREAM_PACKET_HEADER
---

## -description

The **PKTMON_EVT_STREAM_PACKET_HEADER** structure contains a packet header used for event streaming.

## -struct-fields

### -field EventId

The streaming event ID.

### -field PacketDescriptor

The **[PKTMON_EVT_STREAM_PACKET_DESCRIPTOR](ns-pktmonnpik-pktmon_evt_stream_packet_descriptor.md)** portion of the header.

### -field Metadata

The **[PKTMON_EVT_STREAM_METADATA](ns-pktmonnpik-pktmon_evt_stream_metadata.md)** portion of the header.

## -remarks

## -see-also

- **[PKTMON_EVT_STREAM_PACKET_DESCRIPTOR](ns-pktmonnpik-pktmon_evt_stream_packet_descriptor.md)**
- **[PKTMON_EVT_STREAM_METADATA](ns-pktmonnpik-pktmon_evt_stream_metadata.md)**
