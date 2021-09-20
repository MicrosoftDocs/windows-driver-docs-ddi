---
UID: NC:acxelements.EVT_ACX_PEAKMETER_RETRIEVE_LEVEL
tech.root: audio 
title: EVT_ACX_PEAKMETER_RETRIEVE_LEVEL
ms.date: 09/16/2021
targetos: Windows
description: TBD - EVT_ACX_PEAKMETER_RETRIEVE_LEVEL tells the driver that a request to retrieve the peakmeter level has made???.
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
 - EVT_ACX_PEAKMETER_RETRIEVE_LEVEL
f1_keywords:
 - EVT_ACX_PEAKMETER_RETRIEVE_LEVEL
 - acxelements/EVT_ACX_PEAKMETER_RETRIEVE_LEVEL
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_PEAKMETER_RETRIEVE_LEVEL tells the driver that a request to retrieve the peakmeter level has been made???.

## -parameters

### -param PeakMeter

An existing, initialized, ACXPEAKMETER object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Channel

TBD - A number that represents the channel that is active (present -TBD?)

### -param Level

A returned value that indicates the peakmeter level.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_PEAKMETER_RETRIEVE_LEVEL    CodecR_EvtPeakMeterRetrieveLevelCallback;

NTSTATUS
NTAPI
CodecR_EvtPeakMeterRetrieveLevelCallback(
    _In_    ACXPEAKMETER    PeakMeter,
    _In_    ULONG           Channel,
    _Out_   LONG *          PeakMeterLevel
    )
{
    PAGED_CODE();

    ASSERT(PeakMeter);
    PCODEC_PEAKMETER_ELEMENT_CONTEXT peakmeterCtx = GetCodecPeakMeterElementContext(PeakMeter);
    ASSERT(peakmeterCtx);

    if (Channel == ALL_CHANNELS_ID)
    {
        Channel = 0;
    }

    *PeakMeterLevel = peakmeterCtx->PeakMeterLevel[Channel];

    return STATUS_SUCCESS;
}
```

## -see-also

[acxelements.h header](index.md)

