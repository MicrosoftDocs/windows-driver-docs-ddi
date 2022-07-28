---
UID: NC:acxstreams.EVT_ACX_STREAM_PREPARE_HARDWARE
tech.root: audio
title: EVT_ACX_STREAM_PREPARE_HARDWARE
ms.date: 06/22/2022
targetos: Windows
description: The EvtAcxStreamPrepareHardware event tells the driver to prepare the hardware for streaming.
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
 - EVT_ACX_STREAM_PREPARE_HARDWARE
f1_keywords:
 - EVT_ACX_STREAM_PREPARE_HARDWARE
 - acxstreams/EVT_ACX_STREAM_PREPARE_HARDWARE
dev_langs:
 - c++
---

## -description

The EvtAcxStreamPrepareHardware event tells the driver to prepare the hardware for streaming. 

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxStream supports different states. These states indicate when audio is flowing (RUN state), audio is not flowing but audio hardware is prepared (PAUSE state), or audio is not flowing and audio hardware is not prepared (STOP state).

The EvtAcxStreamPrepareHardware event will transition the stream state from the Stop state to the Pause state. The driver should allocate any hardware resources needed for streaming in this event, such as DMA engines.


Once the stream is in the Pause state, the driver may receive the [EvtAcxStreamRun](nc-acxstreams-evt_acx_stream_run.md) event to transition to the Run state or the driver may receive the [EvtAcxStreamReleaseHardware](nc-acxstreams-evt_acx_stream_release_hardware.md) event to transition to the Stop state.

ACX Events are analogous to KS states as described in this table.

| Start State | End State | ACX Driver Event Called | Notes                                                 |
|-------------|-----------|-------------------------|-------------------------------------------------------|
| STOP        | ACQUIRE   | PrepareHardware         | Driver performs hardware allocations and preparations |
| ACQUIRE     | PAUSE     | (No Call)               |                                                       |
| PAUSE       | RUN       | Run                     |                                                       |
| RUN         | PAUSE     | Pause                   |                                                       |
| PAUSE       | ACQUIRE   | (No call)               |                                                       |
| ACQUIRE     | STOP      | ReleaseHardware         | Driver releases hardware allocations                  |

[EvtAcxStreamAllocateRtPackets](nc-acxstreams-evt_acx_stream_allocate_rtpackets.md) is called before EvtAcxStreamPrepareHardware to allow the RT packet allocation to occur before EvtAcxStreamPrepareHardware.

**Buffer allocations and DMA**

The buffer allocation typically only involves allocating system memory in such a way that it can be used with the DMA hardware. Typically, the buffer allocation will not have any effect on the streaming hardware. The prepare hardware phase is used as the driver is getting the stream ready to run, by completing tasks such as reserving bandwidth, programming DMA, and completing the preparation for the request to run the stream. Typically, the prepare hardware code will make use of the allocated buffers for preparing the DMA and related activities to be ready to start the stream.

**Memory Cleanup**

The packet allocations (physical memory on the system) is done before the EvtAcxStreamPrepareHardware, and their release (EvtAcxStreamFreeRtPackets) is done after EvtAcxStreamReleaseHardware. This pattern is an existing legacy behavior that is embedded in the upper layers audio stream setup flow (ks allocate buffer prop init). 

The disposal of the stream’s resources can be done in the driver’s stream context cleanup (not destroy).  Never put the disposal of anything that is shared in an object’s context destroy callback. This guidance applies to all the ACX objects. 

The destroy callback is invoked after the last ref is gone, when it is unknown. 

The stream’s cleanup callback is called when the handle is closed. One exception to this is when the driver created the stream in its callback. If ACX failed to add this stream to its stream-bridge just before returning from the stream-create operation, the stream is cancelled async, and the current thread returns an error to the create-stream client. The stream should not have any mem allocations allocated at this point.


### Example

Example usage is shown below.

```cpp
    ACX_STREAM_CALLBACKS streamCallbacks;
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPrepareHardware     = Codec_EvtStreamPrepareHardware;
    ...
    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);
```

```cpp
#pragma code_seg("PAGE")
NTSTATUS
Codec_EvtStreamPrepareHardware(
    _In_ ACXSTREAM Stream
    )
{
    PSTREAM_CONTEXT ctx;
    NTSTATUS        status;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);

    status = AllocateStreamHardware(Stream);

    if (NT_SUCCESS(status))
    {
        ctx->StreamState = AcxStreamStatePause;
    }

    return status;
}
```

## -see-also

- [acxstreams.h header](index.md)
- [EVT_ACX_STREAM_RUN_HARDWARE](nc-acxstreams-evt_acx_stream_run.md)
- [EVT_ACX_STREAM_PAUSE_HARDWARE](nc-acxstreams-evt_acx_stream_pause.md)
- [EVT_ACX_STREAM_RELEASE_HARDWARE](nc-acxstreams-evt_acx_stream_release_hardware.md)

