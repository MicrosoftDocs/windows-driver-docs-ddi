---
UID: NC:acxstreams.EVT_ACX_STREAM_GET_HW_LATENCY
tech.root: audio
title: EVT_ACX_STREAM_GET_HW_LATENCY
ms.date: 01/25/2022
targetos: Windows
description: The EvtAcxStreamGetHwLatency event tells the driver to provide stream latency for the specific circuit of this stream (overall latency will be a sum of the latency of the different circuits). 
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
 - EVT_ACX_STREAM_GET_HW_LATENCY
f1_keywords:
 - EVT_ACX_STREAM_GET_HW_LATENCY
 - acxstreams/EVT_ACX_STREAM_GET_HW_LATENCY
dev_langs:
 - c++
---

## -description

The EvtAcxStreamGetHwLatency event tells the driver to provide stream latency for the specific circuit of this stream (overall latency will be a sum of the latency of the different circuits).

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param FifoSize

The FifoSize in bytes.

### -param Delay

The Delay in 100-nanosecond units.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).
 
## -remarks

Example usage is shown below.

```cpp
    //
    // Init streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    
    rtCallbacks.EvtAcxStreamGetHwLatency = EvtStreamGetHwLatency;

    status = AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks));
```

```cpp
PAGED_CODE_SEG
NTSTATUS
EvtStreamGetHwLatency(
    _In_ ACXSTREAM Stream,
    _Out_ ULONG * FifoSize,
    _Out_ ULONG * Delay
)
{
    PSTREAM_CONTEXT ctx;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);

    *FifoSize = ctx->DmaFifoSize;
    *Delay = ctx->ChipsetDelay + ctx->CodecDelay;

    return STATUS_SUCCESS;
}
```


## -see-also

- [acxstreams.h header](index.md)

