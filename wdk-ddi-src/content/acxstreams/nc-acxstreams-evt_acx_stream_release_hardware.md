---
UID: NC:acxstreams.EVT_ACX_STREAM_RELEASE_HARDWARE
tech.root: audio
title: EVT_ACX_STREAM_RELEASE_HARDWARE
ms.date: 07/28/2022
targetos: Windows
description: The EvtAcxStreamReleaseHardware event tells the driver to release any hardware allocated for the stream and put the stream into the Stop state.
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
 - EVT_ACX_STREAM_RELEASE_HARDWARE
f1_keywords:
 - EVT_ACX_STREAM_RELEASE_HARDWARE
 - acxstreams/EVT_ACX_STREAM_RELEASE_HARDWARE
dev_langs:
 - c++
---

## -description

The **EvtAcxStreamReleaseHardware** event tells the driver to release any hardware allocated for the stream and put the stream into the Stop state. 

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

An AcxStream supports different states. These states indicate when audio is flowing (RUN state), audio is not flowing but audio hardware is prepared (PAUSE state), or audio is not flowing and audio hardware is not prepared (STOP state).

The EvtAcxStreamReleaseHardware event will transition the stream state from the Pause state to the Stop state. The driver should release any hardware resources that were allocated for streaming in this event, such as DMA engines. Once the stream is in the Stop state, the driver may receive the [EvtAcxStreamPrepareHardware](nc-acxstreams-evt_acx_stream_prepare_hardware.md) event to transition to the Pause state or the ACXSTREAM object may be destroyed.

ACX Events are analogous to KS states as described in this table.

| Start State | End State | ACX Driver Event Called | Notes                                                 |
|-------------|-----------|-------------------------|-------------------------------------------------------|
| STOP        | ACQUIRE   | PrepareHardware         | Driver performs hardware allocations and preparations |
| ACQUIRE     | PAUSE     | (No Call)               |                                                       |
| PAUSE       | RUN       | Run                     |                                                       |
| RUN         | PAUSE     | Pause                   |                                                       |
| PAUSE       | ACQUIRE   | (No call)               |                                                       |
| ACQUIRE     | STOP      | ReleaseHardware         | Driver releases hardware allocations                  |

When work with the stream is complete, [EvtAcxStreamFreeRtPackets](nc-acxstreams-evt_acx_stream_free_rtpackets.md) is called after EvtAcxStreamReleaseHardware. This allows the release hardware phase to finish deallocating bandwidth, freeing DMA resources and any other associated cleanup, to occur before the allocated RT buffers are then freed.

**Memory Cleanup**

The disposal of the stream’s resources can be done in the driver’s stream context cleanup (not destroy).  Never put the disposal of anything that is shared in an object’s context destroy callback. This guidance applies to all the ACX objects. 

The destroy callback is invoked after the last ref is gone, when it is unknown. 

The stream’s cleanup callback is called when the handle is closed. One exception to this is when the driver created the stream in its callback. If ACX failed to add this stream to its stream-bridge just before returning from the stream-create operation, the stream is cancelled async, and the current thread returns an error to the create-stream client. The stream should not have any mem allocations allocated at this point.

### Example

Example usage is shown below.

```cpp
    ACX_STREAM_CALLBACKS streamCallbacks;
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamReleaseHardware = EvtStreamReleaseHardware;
    ...
    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);
```

```cpp
PAGED_CODE_SEG
NTSTATUS
EvtStreamReleaseHardware(
    _In_ ACXSTREAM Stream
    )
{
    PSTREAM_CONTEXT ctx;
    NTSTATUS        status;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);

    status = ReleaseStreamHardware(Stream);

    ctx->StreamState = AcxStreamStateStop;

    return status;
}
```

## -see-also

- [acxstreams.h header](index.md)
- [EVT_ACX_STREAM_PREPARE_HARDWARE](nc-acxstreams-evt_acx_stream_prepare_hardware.md)
- [EVT_ACX_STREAM_RUN_HARDWARE](nc-acxstreams-evt_acx_stream_run.md)
- [EVT_ACX_STREAM_PAUSE_HARDWARE](nc-acxstreams-evt_acx_stream_pause.md)


