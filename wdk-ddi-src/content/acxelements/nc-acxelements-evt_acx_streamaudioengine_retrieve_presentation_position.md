---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
ms.date: 09/20/2021
targetos: Windows
description: TBD - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION tells the driver that a request to retrieve the presentation position has been made???.
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
 - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION tells the driver that a request to retrieve the presentation position has been made???.

## -parameters

### -param StreamAudioEngine

An ACXSTREAMAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PositionInBlocks

TBD TBD TBD - This is from the KSAUDIO_PRESENTATION_POSITION structure, should that be used here?

Specifies the block offset from the start of the stream to the current post-decoded, uncompressed position in the stream. A "block" refers to the group of channels in the same sample. So, for example, in a PCM stream a block is the same as a frame. However, for compressed formats a block is a single sample within a frame. This means that for a typical MP3 stream that has 1152 samples in a frame, there are 1152 blocks. 

### -param QPCPosition

TBD TBD TBD - This is from the KSAUDIO_PRESENTATION_POSITION structure, should that be used here?

Specifies the value of the performance counter at the time that the audio driver reads the presentation position in response to the KSAUDIO_PRESENTATION_POSITION call (TBD Something else in ACX???) . A driver writes to this field with the value read from calling KeQueryPerformanceCounter when a snapshot is taken of the presentation position.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION    CodecR_EvtAcxStreamAudioEngineRetrievePresentationPosition;

NTSTATUS
CodecR_EvtAcxStreamAudioEngineRetrievePresentationPosition(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _Out_   PULONGLONG              PositionInBlocks,
    _Out_   PULONGLONG              QPCPosition
)
{
    NTSTATUS status = STATUS_INVALID_PARAMETER;
    ACXSTREAM stream;
    PCODEC_STREAM_CONTEXT ctx;
    CRenderStreamEngine * streamEngine = NULL;

    PAGED_CODE();

    stream = AcxStreamAudioEngineGetStream(StreamAudioEngine);
    if (stream)
    {
        ctx = GetCodecStreamContext(stream);

        streamEngine = static_cast<CRenderStreamEngine*>(ctx->StreamEngine);

        status = streamEngine->GetPresentationPosition(PositionInBlocks, QPCPosition);
    }

    return status;
}
```

## -see-also

[acxelements.h header](index.md)

