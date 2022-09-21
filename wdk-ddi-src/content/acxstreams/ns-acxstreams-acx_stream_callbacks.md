---
UID: NS:acxstreams._ACX_STREAM_CALLBACKS
tech.root: audio
title: ACX_STREAM_CALLBACKS
ms.date: 08/01/2022
targetos: Windows
description: The ACX_STREAM_CALLBACKS structure identifies the driver callbacks for streaming to the ACX framework. 
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
req.typenames: ACX_STREAM_CALLBACKS, *PACX_STREAM_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACX_STREAM_CALLBACKS
 - PACX_STREAM_CALLBACKS
 - ACX_STREAM_CALLBACKS
f1_keywords:
 - _ACX_STREAM_CALLBACKS
 - acxstreams/_ACX_STREAM_CALLBACKS
 - PACX_STREAM_CALLBACKS
 - acxstreams/PACX_STREAM_CALLBACKS
 - ACX_STREAM_CALLBACKS
 - acxstreams/ACX_STREAM_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_STREAM_CALLBACKS** structure identifies the driver callbacks for streaming to the ACX framework. This structure is a part of the [ACX_PIN_CONFIG structure](/windows-hardware/drivers/ddi/acxpin/ns-acxpin-acx_pin_config).

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxStreamPrepareHardware

The [PFN_ACX_STREAM_PREPARE_HARDWARE](nc-acxstreams-evt_acx_stream_prepare_hardware.md) Callback.

### -field EvtAcxStreamReleaseHardware

The [PFN_ACX_STREAM_RELEASE_HARDWARE](nc-acxstreams-evt_acx_stream_release_hardware.md) Callback.

### -field EvtAcxStreamRun

The [PFN_ACX_STREAM_RUN](nc-acxstreams-evt_acx_stream_run.md) Callback.

### -field EvtAcxStreamPause

The [PFN_ACX_STREAM_PAUSE](nc-acxstreams-evt_acx_stream_pause.md) Callback.

### -field EvtAcxStreamAssignDrmContentId

The [EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID](nc-acxstreams-evt_acx_stream_assign_drm_content_id.md) Callback.

## -remarks

For RT streaming, the driver will also define and use the [ACX_RT_STREAM_CALLBACKS](ns-acxstreams-acx_rt_stream_callbacks.md).

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
- [AcxStreamInitAssignAcxStreamCallbacks](nf-acxstreams-acxstreaminitassignacxstreamcallbacks.md)

