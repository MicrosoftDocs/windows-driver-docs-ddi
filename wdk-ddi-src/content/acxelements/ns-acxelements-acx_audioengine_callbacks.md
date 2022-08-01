---
UID: NS:acxelements._ACX_AUDIOENGINE_CALLBACKS
tech.root: audio 
title: ACX_AUDIOENGINE_CALLBACKS
ms.date: 07/27/2022
targetos: Windows
description: The ACX_AUDIOENGINE_CALLBACKS structure defines callbacks for the ACX audio engine. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_AUDIOENGINE_CALLBACKS, *PACX_AUDIOENGINE_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_AUDIOENGINE_CALLBACKS
 - PACX_AUDIOENGINE_CALLBACKS
 - ACX_AUDIOENGINE_CALLBACKS
f1_keywords:
 - _ACX_AUDIOENGINE_CALLBACKS
 - acxelements/_ACX_AUDIOENGINE_CALLBACKS
 - PACX_AUDIOENGINE_CALLBACKS
 - acxelements/PACX_AUDIOENGINE_CALLBACKS
 - ACX_AUDIOENGINE_CALLBACKS
 - acxelements/ACX_AUDIOENGINE_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_AUDIOENGINE_CALLBACKS** structure defines callbacks for the ACX audio engine. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxAudioEngineRetrieveBufferSizeLimits

The [EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS](nc-acxelements-evt_acx_audioengine_retrieve_buffer_size_limits.md) callback.

### -field EvtAcxAudioEngineAssignEffectsState

The [EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE](nc-acxelements-evt_acx_audioengine_assign_effects_state.md) callback.

### -field EvtAcxAudioEngineRetrieveEffectsState

The [EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE](nc-acxelements-evt_acx_audioengine_retrieve_effects_state.md) callback.

### -field EvtAcxAudioEngineRetrieveEngineMixFormat

The [EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT](nc-acxelements-evt_acx_audioengine_retrieve_engine_format.md) callback.

### -field EvtAcxAudioEngineAssignEngineDeviceFormat

The [EVT_ACX_AUDIOENGINE_ASSIGN_ENGINE_FORMAT](nc-acxelements-evt_acx_audioengine_assign_engine_format.md) callback.

### -field EvtAcxAudioEngineProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/acxrequest/nc-acxrequest-evt_acx_object_process_request) callback. 

## -remarks

### Example

Example usage is shown below.

```cpp
  ACX_AUDIOENGINE_CALLBACKS       audioEngineCallbacks;

  ACX_AUDIOENGINE_CALLBACKS_INIT(&audioEngineCallbacks);
    audioEngineCallbacks.EvtAcxAudioEngineRetrieveBufferSizeLimits = CodecR_EvtAcxAudioEngineRetrieveBufferSizeLimits;
    audioEngineCallbacks.EvtAcxAudioEngineAssignEffectsState = CodecR_EvtAcxAudioEngineAssignEffectsState;
    audioEngineCallbacks.EvtAcxAudioEngineRetrieveEffectsState = CodecR_EvtAcxAudioEngineRetrieveEffectsState;
    audioEngineCallbacks.EvtAcxAudioEngineRetrieveEngineMixFormat = CodecR_EvtAcxAudioEngineRetrieveEngineMixFormat;
    audioEngineCallbacks.EvtAcxAudioEngineAssignEngineDeviceFormat = CodecR_EvtAcxAudioEngineAssignEngineDeviceFormat;

```

## -see-also

- [acxelements.h header](index.md)


