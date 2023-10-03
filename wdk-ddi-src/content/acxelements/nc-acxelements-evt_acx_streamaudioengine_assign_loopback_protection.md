---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
tech.root: audio
title: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
ms.date: 12/15/2022
targetos: Windows
description: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION is implemented by the driver and is called when the loopback protection status is set for a stream audio engine node.
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
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
dev_langs:
 - c++
---

## -description

The **EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION** callback is implemented by the driver and is called when the loopback protection status is set for an audio engine node.

## -parameters

### -param StreamAudioEngine

An existing, initialized, ACXSTREAMAUDIOENGINE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ConstrictorOption

The [ACX_CONSTRICTOR_OPTION](ne-acxelements-acx_constrictor_option.md) that specifies the loopback protection status of the stream audio engine. The status can either be set to AcxConstrictorOptionNone or AcxConstrictorOptionMute. If there are any active streams with AcxConstrictorOptionMute in effect, then the loopback tap for this audio output will emit silence. If all the active stream have AcxConstrictorOptionNone in effect, then the loopback tap contains meaningful data.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION        CodecR_EvtAcxStreamAudioEngineAssignLoopbackProtection;

NTSTATUS
CodecR_EvtAcxStreamAudioEngineAssignLoopbackProtection(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _In_    ACX_CONSTRICTOR_OPTION  ConstrictorOption
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

        status = streamEngine->SetLoopbackProtection(ConstrictorOption);
    }

    return status;
}

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
