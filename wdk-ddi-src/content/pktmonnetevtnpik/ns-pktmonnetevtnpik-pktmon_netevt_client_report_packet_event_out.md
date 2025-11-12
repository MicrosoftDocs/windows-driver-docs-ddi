---
UID: NS:pktmonnetevtnpik._PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
tech.root: netvista
title: PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
ms.date: 11/12/2025
targetos: Windows
description: The **PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT** structure contains the start and end pointers of the buffer containing packet event information.
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
req.typenames: PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
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
 - _PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
 - PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
f1_keywords:
 - _PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
 - pktmonnetevtnpik/_PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
 - PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
 - pktmonnetevtnpik/PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT
---

## -description

The **PKTMON_NETEVT_CLIENT_REPORT_PACKET_EVENT_OUT** structure contains the start and end pointers of the buffer containing packet event information. This structure is used as an output parameter when reporting packet flow events through the NetEvt interface.

## -struct-fields

### -field BufferStart

Pointer to the beginning of the buffer containing the packet event information. This marks the starting address of the event data that has been written.

### -field BufferEnd

Pointer to the end of the buffer containing the packet event information. This marks the address immediately after the last byte of valid event data.

## -remarks

The buffer bounded by *BufferStart* and *BufferEnd* typically contains a **[PKTMON_EVT_STREAM_PACKET_HEADER](ns-pktmonnetevtnpik-pktmon_evt_stream_packet_header.md)** followed by the packet metadata and payload data.

## -see-also

- [PKTMON_EVT_STREAM_PACKET_HEADER](ns-pktmonnetevtnpik-pktmon_evt_stream_packet_header.md)
- [PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT](ns-pktmonnetevtnpik-pktmon_netevt_client_report_packet_drop_out.md)
- [PKTMON_NETEVT_PROVIDER_DISPATCH](ns-pktmonnetevtnpik-pktmon_netevt_provider_dispatch.md)

