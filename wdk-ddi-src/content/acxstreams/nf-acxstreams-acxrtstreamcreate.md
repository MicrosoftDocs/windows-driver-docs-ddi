---
UID: NF:acxstreams.AcxRtStreamCreate
tech.root: audio
title: AcxRtStreamCreate
ms.date: 02/10/2022
targetos: Windows
description: AcxRtStreamCreate creates an ACX RT-based Stream that is used by the OS to stream audio data.
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
 - AcxRtStreamCreate
f1_keywords:
 - AcxRtStreamCreate
 - acxstreams/AcxRtStreamCreate
dev_langs:
 - c++
---

## -description

AcxRtStreamCreate creates an ACX RTStream audio stream that is used by the OS to stream audio data.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT and its stream.

### -param Circuit

The ACXCIRCUIT that this stream will be associated with.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object’s values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An ACXSTREAM_INIT structure that defines the initialization parameters of the stream. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

After the ACXSTREAM has been created, the driver can add one or more ACX elements to the stream. By default, ACX elements are connected in the same order of assembly. An ACXSTREAM is associated with only one ACXCIRCUIT. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RealTime (RT) stream objects used by streaming circuits.

The ACXSTREAM created by AcxRtStreamCreate will allow the driver to receive control signals and state changes associated with a stream. The ACXSTREAM will also support streaming audio data to or from the OS. A driver that supports streaming audio data should use AcxRtStreamCreate to create an ACXSTREAM with support for streaming. For an endpoint that is made from multiple ACXCIRCUITs across multiple drivers, the ACXCIRCUIT that hosts the streaming pin would create an ACX RT Stream while the other ACXCIRCUITs in the endpoint would create non-RT ACX Streams.

### Example

Example Rt stream creation is shown below.

```cpp
    //
    // Init streaming callbacks.
    //
    ACX_STREAM_CALLBACKS streamCallbacks;
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPrepareHardware     = EvtStreamPrepareHardware;
    streamCallbacks.EvtAcxStreamReleaseHardware     = EvtStreamReleaseHardware;
    streamCallbacks.EvtAcxStreamRun                 = EvtStreamRun;
    streamCallbacks.EvtAcxStreamPause               = EvtStreamPause;
    streamCallbacks.EvtAcxStreamAssignDrmContentId  = EvtStreamAssignDrmContentId;

    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);

    //
    // Init RT Streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    rtCallbacks.EvtAcxStreamGetHwLatency = EvtStreamGetHwLatency;
    rtCallbacks.EvtAcxStreamAllocateRtPackets = EvtStreamAllocateRtPackets;
    rtCallbacks.EvtAcxStreamFreeRtPackets = EvtStreamFreeRtPackets;
    rtCallbacks.EvtAcxStreamSetRenderPacket = EvtStreamSetRenderPacket;
    rtCallbacks.EvtAcxStreamGetCurrentPacket = EvtStreamGetCurrentPacket;
    rtCallbacks.EvtAcxStreamGetPresentationPosition = EvtStreamGetPresentationPosition;

    status = AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks);

    //
    // Create the stream.
    //
    WDF_OBJECT_ATTRIBUTES attributes;
    ACXSTREAM stream;
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, STREAM_CONTEXT);
    attributes.EvtCleanupCallback = EvtStreamContextCleanup;
    attributes.EvtDestroyCallback = EvtStreamDestroy;
    status = AcxRtStreamCreate(Device, Circuit, &attributes, &StreamInit, &stream);
```

## -see-also

- [acxstreams.h header](index.md)

