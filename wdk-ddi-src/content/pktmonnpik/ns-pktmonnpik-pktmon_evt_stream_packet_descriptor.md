---
UID: NS:pktmonnpik._PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
tech.root: netvista
title: PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
ms.date: 03/13/2025
targetos: Windows
description: The PKTMON_EVT_STREAM_PACKET_DESCRIPTOR structure contains a packet descriptor used for event streaming.
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
req.typenames: PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
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
 - _PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
 - PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
f1_keywords:
 - _PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
 - pktmonnpik/_PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
 - PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
 - pktmonnpik/PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_EVT_STREAM_PACKET_DESCRIPTOR
---

## -description

The **PKTMON_EVT_STREAM_PACKET_DESCRIPTOR** structure contains a packet descriptor used for event streaming.

## -struct-fields

### -field PacketOriginalLength

The original packet length.

### -field PacketLoggedLength

Represents the length of the part of the packet that was logged. This will be same as *PacketOriginalLength* if the packet was not truncated when logged, otherwise it will be shorter.

### -field PacketMetaDataLength

Length of the metadata.

> [!NOTE]
> It's important to rely on *PacketMetaDataLength* instead of the size of structure **[PKTMON_EVT_STREAM_METADATA](ns-pktmonnpik-pktmon_evt_stream_metadata.md)** as this structure might increase in size in future releases.

## -remarks

## -see-also

- **[PKTMON_EVT_STREAM_METADATA](ns-pktmonnpik-pktmon_evt_stream_metadata.md)**
