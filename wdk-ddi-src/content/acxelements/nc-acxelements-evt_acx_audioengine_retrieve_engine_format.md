---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
tech.root: audio 
title: EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT
ms.date: 09/03/2021
targetos: Windows
description: The EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT callback is implemented by the driver and is called when the internal mix format is requested for the specified audio engine. 
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

The EVT_ACX_AUDIOENGINE_RETRIEVE_ENGINE_FORMAT callback is implemented by the driver and is called when the internal mix format is requested for the specified audio engine. 

## -parameters

### -param AudioEngine

The ACXAUDIOENGINE object for which the mix format has been requested. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Format

The ACXDATAFORMAT object that describes the audio engine mix format.

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
READY2GO

## -see-also

- [acxelements.h header](index.md)

