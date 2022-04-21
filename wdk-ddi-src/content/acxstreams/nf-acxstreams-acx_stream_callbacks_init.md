---
UID: NF:acxstreams.ACX_STREAM_CALLBACKS_INIT
tech.root: audio
title: ACX_STREAM_CALLBACKS_INIT
ms.date:  06/16/2021
targetos: Windows
description: The ACX_STREAM_CALLBACKS_INIT function initializes the ACX stream callbacks.
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
 - ACX_STREAM_CALLBACKS_INIT
f1_keywords:
 - ACX_STREAM_CALLBACKS_INIT
 - acxstreams/ACX_STREAM_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_STREAM_CALLBACKS_INIT function initializes the ACX stream callbacks.

## -parameters

### -param Callbacks

A [ACX_STREAM_CALLBACKS](ns-acxstreams-acx_stream_callbacks.md) structure.

## -remarks

### Example

```cpp

  ACX_STREAM_CALLBACKS        streamCallbacks;

    //
    // Init streaming callbacks.
    //
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPrepareHardware = EvtStreamPrepareHardware;
    streamCallbacks.EvtAcxStreamReleaseHardware = EvtStreamReleaseHardware;
    streamCallbacks.EvtAcxStreamRun = EvtStreamRun;
    streamCallbacks.EvtAcxStreamPause = EvtStreamPause;
    streamCallbacks.EvtAcxStreamAssignDrmContentId = EvtStreamAssignDrmContentId;

    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);


```

## -see-also

- [AcxStreamInitAssignAcxStreamCallbacks](nf-acxstreams-acxstreaminitassignacxstreamcallbacks.md)
- [acxstreams.h header](index.md)

TBD - Please review this topic