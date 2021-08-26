---
UID: NC:acxstreams.EVT_ACX_STREAM_RUN
tech.root: audio
title: EVT_ACX_STREAM_RUN
ms.date: 07/08/2021
targetos: Windows
description: The EvtAcxStreamRun event tells the driver when the stream is running. ??? TBD
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
 - EVT_ACX_STREAM_RUN
f1_keywords:
 - EVT_ACX_STREAM_RUN
 - acxstreams/EVT_ACX_STREAM_RUN
dev_langs:
 - c++
---

## -description

The EvtAcxStreamRun event tells the driver when the stream is running. ??? TBD

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

An AcxStream support different states. These states indicate when audio is flowing (RUN state) or not flowing (PAUSE or STOP state).

Once the stream is created and the appropriate buffers are allocated, the stream is in the Pause state awaiting stream start. When the client puts the stream into Play state, the ACX framework will call all circuits associated with the stream to indicate the stream state is in Play. The ACXPIN will then be placed in the Play state, at which point data will start flowing. 

Once the stream is created and the resources are allocated, the application will call Start on the stream to start playback. The client starts by prerolling a buffer. When the client calls ReleaseBuffer, this will translate to a call in AudioKSE that will call into the ACX layer, which will call EvtAcxStreamSetRenderPacket on the active ACXSTREAM. The property will include the packet index (0-based) and, if appropriate, an EOS flag with the byte offset of the end of the stream in the current packet.  

During ACX device power down and removal, if streams are present, ACX SetState callbacks to transition all circuit’s streams to Pause. This is Stream Instance scoped.

### Example

TBD - Need to see if this is the correct code sample


Example usage is shown below.

```cpp
ACX_STREAM_CALLBACKS streamCallbacks;
ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
streamCallbacks.EvtAcxStreamRun = EvtStreamRun;

...

_Use_decl_annotations_
PAGED_CODE_SEG
NTSTATUS
EvtStreamRun(
    _In_ ACXSTREAM Stream
    )
{
    PSTREAM_CONTEXT ctx;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);
    ASSERT(ctx);
    ASSERT(ctx->StreamEngine);

    return ctx->StreamEngine->Run();
}

```

## -see-also

[acxstreams.h header](index.md)

[EVT_ACX_STREAM_PREPARE_HARDWARE](nc-acxstreams-evt_acx_stream_prepare_hardware.md)

[EVT_ACX_STREAM_PAUSE_HARDWARE](nc-acxstreams-evt_acx_stream_pause.md)

[EVT_ACX_STREAM_RELEASE_HARDWARE](nc-acxstreams-evt_acx_stream_release_hardware.md)


