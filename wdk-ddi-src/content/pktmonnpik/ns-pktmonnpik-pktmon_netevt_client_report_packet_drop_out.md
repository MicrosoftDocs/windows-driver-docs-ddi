---
UID: NS:pktmonnpik._PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
tech.root: netvista
title: PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
ms.date: 03/04/2025
targetos: Windows
description: The PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT structure contains the start and end pointer of the buffer containing the dropped packet information.
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
req.typenames: PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
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
 - _PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
 - PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
f1_keywords:
 - _PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
 - pktmonnpik/_PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
 - PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
 - pktmonnpik/PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT
---

## -description

The **PKTMON_NETEVT_CLIENT_REPORT_PACKET_DROP_OUT** structure contains the start and end pointer of the buffer containing the dropped packet information.

## -struct-fields

### -field BufferStart

Pointer to the start of the buffer containing the dropped packet information.

### -field BufferEnd

Pointer to the end of the buffer containing the dropped packet information.

## -remarks

## -see-also

- [PKTMON_EVT_STREAM_PACKET_HEADER](ns-pktmonnpik-pktmon_evt_stream_packet_header.md)
