---
UID: NF:acxstreams.AcxStreamInitAssignAcxRtStreamCallbacks
tech.root: audio
title: AcxStreamInitAssignAcxRtStreamCallbacks
ms.date: 07/13/2021
targetos: Windows
description: The AcxStreamInitAssignAcxRtStreamCallbacks function sets the RT callbacks using an  ACXSTREAM_INIT object.
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
 - AcxStreamInitAssignAcxRtStreamCallbacks
f1_keywords:
 - AcxStreamInitAssignAcxRtStreamCallbacks
 - acxstreams/AcxStreamInitAssignAcxRtStreamCallbacks
dev_langs:
 - c++
---

## -description

The AcxStreamInitAssignAcxRtStreamCallbacks function sets the RT callbacks using an ACXSTREAM_INIT object and a [ACX_RT_STREAM_CALLBACKS structure](ns-acxstreams-acx_rt_stream_callbacks.md). For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param StreamInit

Defined by a ACXSTREAM_INIT object, that is used to define the stream initialization. 

### -param RtStreamCallbacks

An [ACX_RT_STREAM_CALLBACKS structure](ns-acxstreams-acx_rt_stream_callbacks.md) that defines the list of callbacks. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_RT_STREAM_CALLBACKS         rtCallbacks; 
 
    //
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    rtCallbacks.EvtAcxStreamGetHwLatency            = Dsp_EvtStreamGetHwLatency;
    rtCallbacks.EvtAcxStreamAllocateRtPackets       = Dsp_EvtStreamAllocateRtPackets;
    rtCallbacks.EvtAcxStreamFreeRtPackets           = Dsp_EvtStreamFreeRtPackets;
    rtCallbacks.EvtAcxStreamGetCapturePacket        = DspC_EvtStreamGetCapturePacket;
    rtCallbacks.EvtAcxStreamGetCurrentPacket        = Dsp_EvtStreamGetCurrentPacket;
    rtCallbacks.EvtAcxStreamGetPresentationPosition = Dsp_EvtStreamGetPresentationPosition;
    
    status = AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks);
```


## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic