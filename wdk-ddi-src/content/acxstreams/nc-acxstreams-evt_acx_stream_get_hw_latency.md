---
UID: NC:acxstreams.EVT_ACX_STREAM_GET_HW_LATENCY
tech.root: audio
title: EVT_ACX_STREAM_GET_HW_LATENCY
ms.date: 07/07/2021
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

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param FifoSize

The FifoSize in bytes. 

### -param Delay

The Delay in 100-nanosecond units. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).
 
## -remarks

TBD - Can we show code that services the initialized callback?

Example usage is shown below.

```cpp
//
// Init streaming callbacks.
//
ACX_RT_STREAM_CALLBACKS rtCallbacks;
ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
...
rtCallbacks.EvtAcxStreamGetHwLatency = Dsp_EvtStreamGetHwLatency;

RETURN_NTSTATUS_IF_FAILED(AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks));

...

PAGED_CODE_SEG
NTSTATUS
Dsp_EvtStreamGetHwLatency(
    _In_ ACXSTREAM Stream,
    _Out_ ULONG * FifoSize,
    _Out_ ULONG * Delay
)
{
    PDSP_STREAM_CONTEXT ctx;
    CStreamEngine * streamEngine = NULL;

    PAGED_CODE();

    ctx = GetDspStreamContext(Stream);

    streamEngine = (CStreamEngine*)ctx->StreamEngine;

    return streamEngine->GetHWLatency(FifoSize, Delay);
}
```


## -see-also

[acxstreams.h header](index.md)

