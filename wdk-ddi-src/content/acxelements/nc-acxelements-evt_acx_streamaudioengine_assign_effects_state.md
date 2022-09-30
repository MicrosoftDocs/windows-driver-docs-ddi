---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE callback function is implemented by the driver and is called when the local effects state is set for a stream audio engine node. 
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

The **EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE** callback function is implemented by the driver and is called when the local effects state is set for a stream audio engine node.

## -parameters

### -param StreamAudioEngine

An existing, initialized, ACXSTREAMAUDIOENGINE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param State

A ULONG value indicating whether local effect processing in the stream audio engine node is enabled. A nonzero value indicates that processing is enabled. A value of 0 indicates that it is disabled.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_STREAMAUDIOENGINE_ASSIGN_EFFECTS_STATE              DspR_EvtAcxStreamAudioEngineAssignEffectsState;

NTSTATUS
DspR_EvtAcxStreamAudioEngineAssignEffectsState(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _In_    ULONG                   State
)
{
    PAGED_CODE();

    PCODEC_STREAMAUDIOENGINE_CONTEXT pStreamAudioEngineCtx;
    pStreamAudioEngineCtx = GetCodecStreamAudioEngineContext(StreamAudioEngine);

    pStreamAudioEngineCtx->LFxEnabled = (BOOLEAN)State;
    
    return STATUS_SUCCESS;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
