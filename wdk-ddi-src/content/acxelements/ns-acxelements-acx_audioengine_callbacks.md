---
UID: NS:acxelements._ACX_AUDIOENGINE_CALLBACKS
tech.root: audio 
title: ACX_AUDIOENGINE_CALLBACKS
ms.date: 09/01/2021
targetos: Windows
description: 
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

The ACX_RT_STREAM_CALLBACKS structure defines callbacks for RT streaming to the ACX framework. 

## -struct-fields

### -field Size

TBD - The length, in bytes, of this structure.

### -field EvtAcxAudioEngineRetrieveBufferSizeLimits

The [EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS](nc-acxelements-audioengine-retrieve-buffer-size-limits.md) callback.

### -field EvtAcxAudioEngineAssignEffectsState

The [EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS](nc-acxelements-audioengine-assign-effects-states.md) callback.

### -field EvtAcxAudioEngineRetrieveEffectsState

### -field EvtAcxAudioEngineRetrieveEngineMixFormat

### -field EvtAcxAudioEngineAssignEngineDeviceFormat

### -field EvtAcxAudioEngineProcessRequest

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

[acxelements.h header](index.md)

