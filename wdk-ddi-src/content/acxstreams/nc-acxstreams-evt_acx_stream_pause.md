---
UID: NC:acxstreams.EVT_ACX_STREAM_PAUSE
tech.root: audio
title: EVT_ACX_STREAM_PAUSE
ms.date: 07/28/2022
targetos: Windows
description: The EvtAcxStreamPause event tells the driver to transition the stream state from Run to Pause.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - acxstreams.h
api_name:
 - EVT_ACX_STREAM_PAUSE
f1_keywords:
 - EVT_ACX_STREAM_PAUSE
 - acxstreams/EVT_ACX_STREAM_PAUSE
dev_langs:
 - c++
---

## -description

The **EvtAcxStreamPause** event tells the driver to transition the stream state from Run to Pause.

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxStream supports different states. These states indicate when audio is flowing (RUN state), audio is not flowing but audio hardware is prepared (PAUSE state), or audio is not flowing and audio hardware is not prepared (STOP state).

The EvtAcxStreamPause event will transition the stream state from the Run state to the Pause state. Once the stream is in the Pause state, the driver may receive the [EvtAcxStreamRun](nc-acxstreams-evt_acx_stream_run.md) event to transition to the Run state or the driver may receive the [EvtAcxStreamReleaseHardware](nc-acxstreams-evt_acx_stream_release_hardware.md) event to transition to the Stop state.

During ACX device power down and removal, if streams are present, ACX will call the EvtAcxStreamPause to transition streams to Pause. This is Stream Instance scoped.

ACX Events are analogous to KS states as described in this table.

| Start State | End State | ACX Driver Event Called | Notes                                                 |
|-------------|-----------|-------------------------|-------------------------------------------------------|
| STOP        | ACQUIRE   | PrepareHardware         | Driver performs hardware allocations and preparations |
| ACQUIRE     | PAUSE     | (No Call)               |                                                       |
| PAUSE       | RUN       | Run                     |                                                       |
| RUN         | PAUSE     | Pause                   |                                                       |
| PAUSE       | ACQUIRE   | (No call)               |                                                       |
| ACQUIRE     | STOP      | ReleaseHardware         | Driver releases hardware allocations                  |


### Example

Example usage is shown below.

```cpp
    ACX_STREAM_CALLBACKS streamCallbacks;
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPause = EvtStreamPause;
    ...
    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);
```

```cpp
#pragma code_seg("PAGE")
NTSTATUS
EvtStreamPause(
    _In_ ACXSTREAM Stream
    )
{
    PSTREAM_CONTEXT ctx;
    NTSTATUS        status = STATUS_SUCCESS;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);

    status = TransitionStreamToPause(Stream);

    ctx->StreamState = AcxStreamStatePause;

    return status;
}
```

## -see-also

- [acxstreams.h header](index.md)
- [EVT_ACX_STREAM_PREPARE_HARDWARE](nc-acxstreams-evt_acx_stream_prepare_hardware.md)
- [EVT_ACX_STREAM_RUN_HARDWARE](nc-acxstreams-evt_acx_stream_run.md)
- [EVT_ACX_STREAM_RELEASE_HARDWARE](nc-acxstreams-evt_acx_stream_release_hardware.md)


