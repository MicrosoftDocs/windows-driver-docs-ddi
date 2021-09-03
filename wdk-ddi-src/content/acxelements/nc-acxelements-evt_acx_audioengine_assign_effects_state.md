---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
tech.root: audio 
title: EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
ms.date: 09/03/2021
targetos: Windows
description: EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE tells the driver that the audio engine is (?? TBD Preparing) to assign an effects state.  
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
 - EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
f1_keywords:
 - EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
 - acxelements/EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
dev_langs:
 - c++
---

## -description

EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE tells the driver that the audio engine is (?? TBD Preparing) to assign an effects state.  

## -parameters

### -param AudioEngine

An ACXAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param State

TBD - is this the target effects state?

TODO: This is a ulong, but wondering if it would better to reference a state enum such as ACX_STREAM_STATE in the acxstreams header?


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE        DspR_EvtAcxAudioEngineAssignEffectsState;

NTSTATUS
DspR_EvtAcxAudioEngineAssignEffectsState(
    ACXAUDIOENGINE,
    ULONG
)
{
    PAGED_CODE();
    
    // Custom Code goes here

    return STATUS_SUCCESS;
}
```

## -see-also

[acxelements.h header](index.md)

