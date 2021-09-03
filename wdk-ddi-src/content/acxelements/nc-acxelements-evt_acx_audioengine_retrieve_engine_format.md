---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
tech.root: audio 
title: EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
ms.date: 09/03/2021
targetos: Windows
description: TBD - EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT tells the driver to that the audio engine is (?? TBD has ) retrieving the audio engine format.
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
 - LibDef
api_location:
 - acxelements.h
api_name:
 - EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
f1_keywords:
 - EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
 - acxelements/EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT tells the driver to that the audio engine is (?? TBD has ) retrieving the audio engine format.

## -parameters

### -param AudioEngine

An ACXAUDIOENGINE audio engine object that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Format

TBD - An ACXDATAFORMAT object that describes the engine format.

TBD - A TBD type of audio format that is / will be used by the audio engine.

KSPROPERTY_PIN_PROPOSEDATAFORMAT WAVEFORMAT EXTENSIBLE?

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - test code

Example usage is shown below.

```cpp
EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT      CodecR_EvtAcxAudioEngineRetrieveEngineMixFormat;

NTSTATUS
NTAPI
CodecR_EvtAcxAudioEngineRetrieveEngineMixFormat(
    _In_    ACXAUDIOENGINE  AudioEngine,
    _Out_   ACXDATAFORMAT * Format
    )
{
    PCODEC_ENGINE_CONTEXT   audioEngineCtx;
    PAGED_CODE();

    audioEngineCtx = GetCodecEngineContext(AudioEngine);

    if (!audioEngineCtx->MixFormat)
    {
        return STATUS_INVALID_DEVICE_STATE;
    }

    *Format = audioEngineCtx->MixFormat;

    return STATUS_SUCCESS;
}
```

## -see-also

[acxelements.h header](index.md)

