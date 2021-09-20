---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
ms.date: 09/20/2021
targetos: Windows
description: TBD - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE tells the driver that a request to assign the current effects state has made???.
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
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE tells the driver that a request to assign the current effects state has been made???.

## -parameters

### -param StreamAudioEngine

An ACXSTREAMAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param State

TBD - is this the assign effects state?

TODO: This is a ulong, but wondering if it would better to reference a state enum such as ACX_STREAM_STATE?


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - No call back implementation code found.

```cpp
EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE              CodecR_EvtAcxStreamAudioEngineAssignEffectsState;

NTSTATUS
DspR_EvtAcxStreamAudioEngineAssignEffectsState(
    ACXSTREAMAUDIOENGINE,
    ULONG
)
{
    PAGED_CODE();
    
    return STATUS_SUCCESS;
}
```

## -see-also

[acxelements.h header](index.md)

