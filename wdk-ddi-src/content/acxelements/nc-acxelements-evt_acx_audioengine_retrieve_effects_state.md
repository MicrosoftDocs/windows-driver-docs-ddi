---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE
tech.root: audio 
title: EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE callback function is implemented by the driver and is called when the global effects state is requested for the specified audio engine node. 
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
 - EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE
f1_keywords:
 - EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE
 - acxelements/EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE** callback function is implemented by the driver and is called when the global effects state is requested for the specified audio engine node. 

## -parameters

### -param AudioEngine

The ACXAUDIOENGINE object for which the global effects state has been requested. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param State

A ULONG value indicating the global effects state of the specified audio engine node. A nonzero value indicates that global effect processing in the audio engine node is enabled and a value of 0 indicates that global effect processing in the audio engine node is disabled.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
typedef struct _CODEC_ENGINE_CONTEXT {
    ACXDATAFORMAT   MixFormat;
    BOOLEAN         GFxEnabled;
} CODEC_ENGINE_CONTEXT, *PCODEC_ENGINE_CONTEXT;

WDF_DECLARE_CONTEXT_TYPE_WITH_NAME(CODEC_ENGINE_CONTEXT, GetCodecEngineContext)

EVT_ACX_AUDIOENGINE_RETRIEVE_EFFECTS_STATE      Codec_EvtAcxAudioEngineRetrieveEffectsState;

NTSTATUS
Codec_EvtAcxAudioEngineRetrieveEffectsState(
    _In_    ACXAUDIOENGINE  AudioEngine,
    _Out_   PULONG          State
)
{
    PAGED_CODE();

    PCODEC_ENGINE_CONTEXT   pAudioEngineCtx;
    pAudioEngineCtx = GetCodecEngineContext(AudioEngine);

    *State = pAudioEngineCtx->GFxEnabled;

    return STATUS_SUCCESS;
}

```


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
