---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION callback function is implemented by the driver and is called when the current write position for the specified stream audio engine is set. 
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
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION
dev_langs:
 - c++
---

## -description

The **EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION** callback function is implemented by the driver and is called when the current write position for the specified stream audio engine is set. 

## -parameters

### -param StreamAudioEngine

An existing, initialized, ACXSTREAMAUDIOENGINE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Position

The current write position for the ACXSTREAMAUDIOENGINE object in bytes. For more information on the position value, see [KSPROPERTY_AUDIO_WAVERT_CURRENT_WRITE_POSITION](/windows-hardware/drivers/audio/ksproperty-audio-wavert-current-write-position).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_STREAMAUDIOENGINE_ASSIGN_CURRENT_WRITE_POSITION     CodecR_EvtAcxStreamAudioEngineAssignCurrentWritePosition;

NTSTATUS
CodecR_EvtAcxStreamAudioEngineAssignCurrentWritePosition(
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

        status = streamEngine->SetCurrentWritePosition(Position);
    }

    return status;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


