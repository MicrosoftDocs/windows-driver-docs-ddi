---
UID: NS:acxelements._ACX_STREAMAUDIOENGINE_CALLBACKS
tech.root: audio 
title: ACX_STREAMAUDIOENGINE_CALLBACKS
ms.date: 09/02/2021
targetos: Windows
description: The ACX_STREAMAUDIOENGINE_CALLBACKS structure identifies the driver callbacks for ACX audio engine stream operations.
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
req.typenames: ACX_STREAMAUDIOENGINE_CALLBACKS, *PACX_STREAMAUDIOENGINE_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_STREAMAUDIOENGINE_CALLBACKS
 - PACX_STREAMAUDIOENGINE_CALLBACKS
 - ACX_STREAMAUDIOENGINE_CALLBACKS
f1_keywords:
 - _ACX_STREAMAUDIOENGINE_CALLBACKS
 - acxelements/_ACX_STREAMAUDIOENGINE_CALLBACKS
 - PACX_STREAMAUDIOENGINE_CALLBACKS
 - acxelements/PACX_STREAMAUDIOENGINE_CALLBACKS
 - ACX_STREAMAUDIOENGINE_CALLBACKS
 - acxelements/ACX_STREAMAUDIOENGINE_CALLBACKS
dev_langs:
 - c++
---

## -description

The ACX_STREAMAUDIOENGINE_CALLBACKS structure identifies the driver callbacks for ACX stream audio engine operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxStreamAudioEngineAssignEffectsState

The [EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE](nc-acxelements-evt_acx_streamaudioengine_assign_effects_state.md) callback.

### -field EvtAcxStreamAudioEngineRetrieveEffectsState

The [EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_EFFECTS_STATE](nc-acxelements-evt_acx_streamaudioengine_retrieve_effects_state.md) callback.

### -field EvtAcxStreamAudioEngineRetrievePresentationPosition

The [EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION](nc-acxelements-evt_acx_streamaudioengine_retrieve_presentation_position.md) callback.

### -field EvtAcxStreamAudioEngineAssignCurrentWritePosition

The [EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION](nc-acxelements-evt_acx_streamaudioengine_assign_current_write_position.md) callback.

### -field EvtAcxStreamAudioEngineRetrieveLinearBufferPosition

The [EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_LINEAR_BUFFER_POSITION](nc-acxelements-evt_acx_streamaudioengine_retrieve_linear_buffer_position.md) callback.

### -field EvtAcxStreamAudioEngineAssignLastBufferPosition

The [EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION](nc-acxelements-evt_acx_streamaudioengine_assign_last_buffer_position.md) callback.

### -field EvtAcxStreamAudioEngineAssignLoopbackProtection

The [EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION](nc-acxelements-evt_acx_streamaudioengine_assign_loopback_protection.md) callback.

### -field EvtAcxStreamAudioEngineProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/acxrequest/nc-acxrequest-evt_acx_object_process_request.md) callback. 

## -remarks

### Example

Example usage is shown below.

```cpp
        ACX_STREAMAUDIOENGINE_CALLBACKS streamAudioEngineCallbacks;

        // Create the AudioEngine element to control offloaded streaming.
        ACX_STREAMAUDIOENGINE_CALLBACKS_INIT(&streamAudioEngineCallbacks);

        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineAssignEffectsState = CodecR_EvtAcxStreamAudioEngineAssignEffectsState;
        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineRetrieveEffectsState = CodecR_EvtAcxStreamAudioEngineRetrieveEffectsState;
        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineRetrievePresentationPosition = CodecR_EvtAcxStreamAudioEngineRetrievePresentationPosition;
        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineAssignCurrentWritePosition = CodecR_EvtAcxStreamAudioEngineAssignCurrentWritePosition;
        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineRetrieveLinearBufferPosition = CodecR_EvtAcxStreamAudioEngineRetrieveLinearBufferPosition;
        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineAssignLastBufferPosition = CodecR_EvtAcxStreamAudioEngineAssignLastBufferPosition;
        streamAudioEngineCallbacks.EvtAcxStreamAudioEngineAssignLoopbackProtection = CodecR_EvtAcxStreamAudioEngineAssignLoopbackProtection;
```

## -see-also

- [acxelements.h header](index.md)

READY2GO

