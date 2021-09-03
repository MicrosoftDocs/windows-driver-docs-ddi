---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
tech.root: audio 
title: EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
ms.date: 09/03/2021
targetos: Windows
description: TBD - EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS tells the driver to that the audio engine is (?? TBD has ) retrieving buffer size limits.
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
 - EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
f1_keywords:
 - EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
 - acxelements/EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS tells the driver to that the audio engine is (?? TBD has ) retrieving buffer size limits.

## -parameters

### -param AudioEngine

An ACXAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Format

TBD - An ACXDATAFORMAT object that describes the engine format.

TBD - A TBD type of audio format that is / will be used by the audio engine.

KSPROPERTY_PIN_PROPOSEDATAFORMAT WAVEFORMAT EXTENSIBLE?

### -param MinBufferSizeInBytes

The minimum audio engine buffer size in bytes.

### -param MaxBufferSizeInBytes

The maximum audio engine buffer size in bytes.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS CodecR_EvtAcxAudioEngineRetrieveBufferSizeLimits;

NTSTATUS
DspR_EvtAcxAudioEngineRetrieveBufferSizeLimits(
    ACXAUDIOENGINE,
    ACXDATAFORMAT   DataFormat,
    PULONG          MinBufferBytes,
    PULONG          MaxBufferBytes
    )
{
    PAGED_CODE();

    ULONG bytesPerSecond = AcxDataFormatGetAverageBytesPerSec(DataFormat);

    *MinBufferBytes = (ULONG) (MIN_AUDIOENGINE_BUFFER_DURATION_IN_MS * bytesPerSecond / 1000);
    *MaxBufferBytes = (ULONG) (MAX_AUDIOENGINE_BUFFER_DURATION_IN_MS * bytesPerSecond / 1000);

    return STATUS_SUCCESS;
}
```

## -see-also

[acxelements.h header](index.md)

