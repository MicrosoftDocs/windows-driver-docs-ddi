---
UID: NS:pktmonnetevtnpik._PKTMON_EVT_STREAM_METADATA
tech.root: netvista
title: PKTMON_EVT_STREAM_METADATA
ms.date: 11/14/2025
targetos: Windows
description: The PKTMON_EVT_STREAM_METADATA structure contains metadata information used for event streaming.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnetevtnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames:
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnetevtnpik.h
api_name:
 - _PKTMON_EVT_STREAM_METADATA
 - PKTMON_EVT_STREAM_METADATA
f1_keywords:
 - _PKTMON_EVT_STREAM_METADATA
 - pktmonnetevtnpik/_PKTMON_EVT_STREAM_METADATA
 - PKTMON_EVT_STREAM_METADATA
 - pktmonnetevtnpik/PKTMON_EVT_STREAM_METADATA
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_EVT_STREAM_METADATA
---

## -description

The **PKTMON_EVT_STREAM_METADATA** structure contains metadata information used for event streaming.

## -struct-fields

### -field PktGroupId

Group Id for packets belonging to the same processor.

### -field PktCount

The number of packets.

### -field AppearanceCount

Packet Count belonging to the same Net Buffer List.

### -field DirectionName

Enum value of [PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md). Specifies the direction for which the packet was reported.

### -field PacketType

Packet Payload type as [PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md).

### -field ComponentId

ID of the component that reported the packet.

### -field EdgeId

Edge ID of the component boundary from which packet was reported. An edge represents a pair of entry and exit points.

### -field FilterId

The filter identifier.

### -field DropReason

Packet drop reason code, defined in the [PKTMON_DROP_REASON](/windows/win32/pktmon/packetmonitor/nf-packetmonitor-packetmonitorcreaterealtimestream#pktmon_drop_reason) enum.

### -field DropLocation

Packet drop location defined in the [PKTMON_DROP_LOCATION](/windows/win32/pktmon/packetmonitor/nf-packetmonitor-packetmonitorcreaterealtimestream#pktmon_drop_location) enum.

### -field ProcNum

Processor number when the packet was reported.

### -field TimeStamp

Timestamp when the packet was reported. This is retrieved using [KeQuerySystemTime](../wdm/nf-wdm-kequerysystemtime-r1.md).

## -remarks

For more information, see the [PacketMonitorCreateRealtimeStream](/windows/win32/pktmon/packetmonitor/nf-packetmonitor-packetmonitorcreaterealtimestream) function.

## -see-also

- [PKTMON_DIRECTION](../pktmonnpik/ne-pktmonnpik-pktmon_direction.md)
- [PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)
- [PKTMON_DROP_REASON](/windows/win32/pktmon/packetmonitor/nf-packetmonitor-packetmonitorcreaterealtimestream#pktmon_drop_reason)
- [PKTMON_DROP_LOCATION](/windows/win32/pktmon/packetmonitor/nf-packetmonitor-packetmonitorcreaterealtimestream#pktmon_drop_location)
- [KeQuerySystemTime](../wdm/nf-wdm-kequerysystemtime-r1.md)
- [PacketMonitorCreateRealtimeStream](/windows/win32/pktmon/packetmonitor/nf-packetmonitor-packetmonitorcreaterealtimestream)
