---
UID: NF:acxelements.AcxStreamAudioEngineGetStream
tech.root: audio 
title: AcxStreamAudioEngineGetStream
ms.date: 04/29/2022
targetos: Windows
description: The AcxStreamAudioEngineGetStream function retrieves the ACXSTREAM object associated with the given stream audio engine object.
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
 - AcxStreamAudioEngineGetStream
f1_keywords:
 - AcxStreamAudioEngineGetStream
 - acxelements/AcxStreamAudioEngineGetStream
dev_langs:
 - c++
---

## -description

The **AcxStreamAudioEngineGetStream** function retrieves the ACXSTREAM object associated with the given stream audio engine object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param StreamAudioEngine

An existing, initialized, ACXSTREAMAUDIOENGINE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
NTSTATUS
DspR_EvtAcxStreamAudioEngineRetrievePresentationPosition(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _Out_   PULONGLONG              PositionInBlocks,
    _Out_   PULONGLONG              QPCPosition
)
{
    NTSTATUS status = STATUS_INVALID_PARAMETER;
    ACXSTREAM stream;
    PDSP_STREAM_CONTEXT ctx;
    COffloadStreamEngine* streamEngine = NULL;

    PAGED_CODE();

    stream = AcxStreamAudioEngineGetStream(StreamAudioEngine);
    if (stream)
    {
        ctx = GetDspStreamContext(stream);

        streamEngine = static_cast<COffloadStreamEngine*>(ctx->StreamEngine);

        status = streamEngine->GetPresentationPosition(PositionInBlocks, QPCPosition);
    }

    return status;
}
```

## -see-also

- [acxelements.h header](index.md)

READY2GO

EDITCOMPLETE

