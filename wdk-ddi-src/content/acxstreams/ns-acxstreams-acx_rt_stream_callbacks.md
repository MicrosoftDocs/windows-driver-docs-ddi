---
UID: NS:acxstreams._ACX_RT_STREAM_CALLBACKS
tech.root: audio
title: ACX_RT_STREAM_CALLBACKS
ms.date:  06/16/2021
targetos: Windows
description: The ACX_RT_STREAM_CALLBACKS structure defines callbacks for RT streaming to the ACX framework. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_RT_STREAM_CALLBACKS, *PACX_RT_STREAM_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACX_RT_STREAM_CALLBACKS
 - PACX_RT_STREAM_CALLBACKS
 - ACX_RT_STREAM_CALLBACKS
f1_keywords:
 - _ACX_RT_STREAM_CALLBACKS
 - acxstreams/_ACX_RT_STREAM_CALLBACKS
 - PACX_RT_STREAM_CALLBACKS
 - acxstreams/PACX_RT_STREAM_CALLBACKS
 - ACX_RT_STREAM_CALLBACKS
 - acxstreams/ACX_RT_STREAM_CALLBACKS
dev_langs:
 - c++
---

## -description

The ACX_RT_STREAM_CALLBACKS structure defines callbacks for RT streaming to the ACX framework. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxStreamGetHwLatency

The [EvtAcxStreamGetHwLatency](nc-acxstreams-evt_acx_stream_get_hw_latency.md) callback.

### -field EvtAcxStreamAllocateRtPackets

The [EvtAcxStreamAllocateRtPackets](nc-acxstreams-evt_acx_stream_allocate_rtpackets.md) callback.

### -field EvtAcxStreamFreeRtPackets

The [EvtAcxStreamFreeRtPackets](nc-acxstreams-evt_acx_stream_free_rtpackets.md) callback.

### -field EvtAcxStreamSetRenderPacket

The [EvtAcxStreamSetRenderPacket](nc-acxstreams-evt_acx_stream_set_render_packet.md) callback.

### -field EvtAcxStreamGetCurrentPacket

The [EvtAcxStreamGetCurrentPacket](nc-acxstreams-evt_acx_stream_get_current_packet.md) callback.

### -field EvtAcxStreamGetCapturePacket

The [EvtAcxStreamGetCapturePacket](nc-acxstreams-evt_acx_stream_get_capture_packet.md) callback.

### -field EvtAcxStreamGetPresentationPosition

The [EvtAcxStreamGetPresentationPosition](nc-acxstreams-evt_acx_stream_get_presentation_position.md) callback.

## -remarks

The driver must also define and use the [ACX_STREAM_CALLBACKS](ns-acxstreams-acx_stream_callbacks.md) structure to create an ACXRTSTREAM

## -see-also

[acxstreams.h header](index.md)
[AcxStreamInitAssignAcxRtStreamCallbacks](nf-acxstreams-acxstreaminitassignacxrtstreamcallbacks.md)

READY2GO
