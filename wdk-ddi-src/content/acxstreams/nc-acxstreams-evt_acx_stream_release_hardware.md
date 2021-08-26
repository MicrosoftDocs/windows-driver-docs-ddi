---
UID: NC:acxstreams.EVT_ACX_STREAM_RELEASE_HARDWARE
tech.root: audio
title: EVT_ACX_STREAM_RELEASE_HARDWARE
ms.date: 08/26/2021
targetos: Windows
description: TBD - The EvtAcxStreamReleaseHardware event tells the driver when the hardware is being released. (TBD has been released?) The driver should clear/uninstall stream hardware in this callback. 
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

TBD - The EvtAcxStreamReleaseHardware event tells the driver when the hardware is being released. (TBD has been released?) The driver should clear/uninstall stream hardware in this callback. 

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

### Example

TBD - Need to see if this is the correct code sample

Example usage is shown below.

```cpp
ACX_STREAM_CALLBACKS streamCallbacks;
ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
streamCallbacks.EvtAcxStreamReleaseHardware = EvtStreamReleaseHardware;

...

PAGED_CODE_SEG
NTSTATUS
EvtStreamReleaseHardware(
    _In_ ACXSTREAM Stream
    )
{
    PSTREAM_CONTEXT ctx;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);
    ASSERT(ctx);

    //
    // Disable 'remote' stream notifications.
    //
    ASSERT(ctx->EventReader);
    ctx->EventReader->DisableEvents();

    //
    // Clear/uninstall stream h/w.
    //
    ASSERT(ctx->StreamEngine);
    return ctx->StreamEngine->ReleaseHardware();
}
```

## -see-also

[acxstreams.h header](index.md)

[EVT_ACX_STREAM_PREPARE_HARDWARE](nc-acxstreams-evt_acx_stream_prepare_hardware.md)

[EVT_ACX_STREAM_RUN_HARDWARE](nc-acxstreams-evt_acx_stream_run.md)

[EVT_ACX_STREAM_PAUSE_HARDWARE](nc-acxstreams-evt_acx_stream_pause.md)


