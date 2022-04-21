---
UID: NF:acxelements.ACX_STREAMAUDIOENGINE_CALLBACKS_INIT
tech.root: audio 
title: ACX_STREAMAUDIOENGINE_CALLBACKS_INIT
ms.date: 09/21/2021
targetos: Windows
description: The ACX_STREAMAUDIOENGINE_CALLBACKS_INIT function initializes a ACX_STREAMAUDIOENGINE_CALLBACKS structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - ACX_STREAMAUDIOENGINE_CALLBACKS_INIT
f1_keywords:
 - ACX_STREAMAUDIOENGINE_CALLBACKS_INIT
 - acxelements/ACX_STREAMAUDIOENGINE_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_STREAMAUDIOENGINE_CALLBACKS_INIT function initializes a [ACX_STREAMAUDIOENGINE_CALLBACKS structure](ns-acxelements-acx_streamaudioengine_callbacks.md). 

## -parameters

### -param Callbacks

A pointer to an initialized [ACX_STREAMAUDIOENGINE_CALLBACKS structure](ns-acxelements-acx_streamaudioengine_callbacks.md). 

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

