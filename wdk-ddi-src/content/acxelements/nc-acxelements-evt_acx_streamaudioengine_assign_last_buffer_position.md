---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION
tech.root: audio
title: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION
ms.date: 12/15/2022
targetos: Windows
description: The EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION callback function is implemented by the driver and is called when the position of the last valid byte in the audio buffer is set for the specified stream audio engine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION
dev_langs:
 - c++
---

## -description

The **EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION** callback function is implemented by the driver and is called when the position of the last valid byte in the audio buffer is set for the specified stream audio engine.

## -parameters

### -param StreamAudioEngine

An existing, initialized, ACXSTREAMAUDIOENGINE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Position

Indicates the position of the last valid byte in the audio buffer of the specified stream audio engine. For more information on the position value, see [KSPROPERTY_AUDIO_WAVERT_CURRENT_WRITE_LASTBUFFER_POSITION](/windows-hardware/drivers/audio/ksproperty-audio-wavert-current-write-lastbuffer-position).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LAST_BUFFER_POSITION       CodecR_EvtAcxStreamAudioEngineAssignLastBufferPosition;

NTSTATUS
CodecR_EvtAcxStreamAudioEngineAssignLastBufferPosition(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _In_    ULONG                   Position
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

        status = streamEngine->SetLastBufferPosition(Position);
    }

    return status;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
