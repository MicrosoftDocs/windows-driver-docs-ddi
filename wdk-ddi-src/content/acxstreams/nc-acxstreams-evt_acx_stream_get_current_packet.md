---
UID: NC:acxstreams.EVT_ACX_STREAM_GET_CURRENT_PACKET
tech.root: audio
title: EVT_ACX_STREAM_GET_CURRENT_PACKET
ms.date: 10/31/2022
targetos: Windows
description: EvtAcxStreamGetCurrentPacket tells the driver to indicate which packet (0-based) is currently being rendered to the hardware or is currently being filled by the capture hardware.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - EVT_ACX_STREAM_GET_CURRENT_PACKET
f1_keywords:
 - EVT_ACX_STREAM_GET_CURRENT_PACKET
 - acxstreams/EVT_ACX_STREAM_GET_CURRENT_PACKET
dev_langs:
 - c++
---

## -description

**EvtAcxStreamGetCurrentPacket** tells the driver to indicate which packet (0-based) is currently being rendered to the hardware or is currently being filled by the capture hardware.

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit's elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param CurrentPacket

A zero based index to the packet that is currently being rendered to the hardware or is currently being filled by the capture hardware.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);

    rtCallbacks.EvtAcxStreamGetCurrentPacket = EvtStreamGetCurrentPacket;

    status = AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks);
```

```cpp
PAGED_CODE_SEG
NTSTATUS
EvtStreamGetCurrentPacket(
    _In_ ACXSTREAM          Stream,
    _Out_ PULONG            CurrentPacket
)
{
    PSTREAM_CONTEXT ctx;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);

    *CurrentPacket = ctx->CurrentPacket;

    return STATUS_SUCCESS;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
