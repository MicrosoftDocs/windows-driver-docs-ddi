---
UID: NF:acxstreams.AcxStreamInitAssignAcxStreamCallbacks
tech.root: audio
title: AcxStreamInitAssignAcxStreamCallbacks
ms.date: 07/14/2021
targetos: Windows
description: The AcxStreamInitAssignAcxStreamCallbacks function sets the callbacks using an an ACX_STREAM_CALLBACKS structure and a ACXSTREAM_INIT object.
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
 - AcxStreamInitAssignAcxStreamCallbacks
f1_keywords:
 - AcxStreamInitAssignAcxStreamCallbacks
 - acxstreams/AcxStreamInitAssignAcxStreamCallbacks
dev_langs:
 - c++
---

## -description

The AcxStreamInitAssignAcxStreamCallbacks function sets the callbacks using an an [ACX_STREAM_CALLBACKS structure](ns-acxstreams-acx_stream_callbacks.md) and a ACXSTREAM_INIT object.  For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param StreamInit

Defined by a ACXSTREAM_INIT object, that is used to define the stream initialization. 

### -param StreamCallbacks

An [ACX_STREAM_CALLBACKS structure](An [ACX_STREAM_CALLBACKS structure](ns-acxstreams-acx_stream_callbacks.md) that is used to define the following callbacks.

- PFN_ACX_STREAM_PREPARE_HARDWARE
- PFN_ACX_STREAM_RELEASE_HARDWARE
- PFN_ACX_STREAM_RUN
- PFN_ACX_STREAM_PAUSE
- PFN_ACX_STREAM_ASSIGN_DRM_CONTENT_ID

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_STREAM_CALLBACKS            streamCallbacks;
    //
    // Init streaming callbacks.
    //
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPrepareHardware     = Dsp_EvtStreamPrepareHardware;
    streamCallbacks.EvtAcxStreamReleaseHardware     = Dsp_EvtStreamReleaseHardware;
    streamCallbacks.EvtAcxStreamRun                 = Dsp_EvtStreamRun;
    streamCallbacks.EvtAcxStreamPause               = Dsp_EvtStreamPause;

    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);
```


## -see-also

[acxstreams.h header](index.md)

