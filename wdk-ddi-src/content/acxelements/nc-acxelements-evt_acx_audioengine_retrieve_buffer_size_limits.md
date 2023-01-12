---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
tech.root: audio
title: EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
ms.date: 12/15/2022
targetos: Windows
description: The EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS callback is implemented by the driver and is called when the buffer size limits for a given data format are requested for the specified audio engine.
prerelease: true
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
 - EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
f1_keywords:
 - EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
 - acxelements/EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS
dev_langs:
 - c++
---

## -description

The **EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS** callback is implemented by the driver and is called when the buffer size limits for a given data format are requested for the specified audio engine.

## -parameters

### -param AudioEngine

The ACXAUDIOENGINE object for which the buffer size limits have been requested. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Format

The ACXDATAFORMAT for which the callback is determining the min and max buffer sizes the audio engine can accomodate it with.

### -param MinBufferSizeInBytes

The minimum size of buffer that the hardware audio engine can support for the given data format, at the instance when it is called. The buffer size is specified in bytes.

### -param MaxBufferSizeInBytes

The maximum size of buffer that the hardware audio engine can support for the given data format, at the instance when it is called. The buffer size is specified in bytes.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_AUDIOENGINE_RETRIEVE_BUFFER_SIZE_LIMITS CodecR_EvtAcxAudioEngineRetrieveBufferSizeLimits;

NTSTATUS
CodecR_EvtAcxAudioEngineRetrieveBufferSizeLimits(
    _In_    ACXAUDIOENGINE  AudioEngine,
    _In_    ACXDATAFORMAT   DataFormat,
    _Out_   PULONG          MinBufferBytes,
    _Out_   PULONG          MaxBufferBytes
    )
{
    PAGED_CODE();

    ULONG bytesPerSecond = AcxDataFormatGetAverageBytesPerSec(DataFormat);

    *MinBufferBytes = (ULONG) (MIN_AUDIOENGINE_BUFFER_DURATION_IN_MS * bytesPerSecond / 1000);
    *MaxBufferBytes = (ULONG) (MAX_AUDIOENGINE_BUFFER_DURATION_IN_MS * bytesPerSecond / 1000);

    return STATUS_SUCCESS;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
