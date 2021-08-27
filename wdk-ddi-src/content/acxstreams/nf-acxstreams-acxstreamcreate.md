---
UID: NF:acxstreams.AcxStreamCreate
tech.root: audio
title: AcxStreamCreate
ms.date: 08/27/2021
targetos: Windows
description: AcxStreamCreate creates an ACX Stream, defined by a ACXSTREAM_INIT object, that is used to TBD and TBD.
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
 - AcxStreamCreate
f1_keywords:
 - AcxStreamCreate
 - acxstreams/AcxStreamCreate
dev_langs:
 - c++
---

## -description

AcxStreamCreate creates an ACX Stream, defined by a ACXSTREAM_INIT object, that is used to TBD and TBD. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that has/is TBD been TBD.

### -param Circuit

And ACXCIRCUT that will be TBD.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to TBD. 

### -param Config

An ACXSTREAM_INIT Config structure TBD.

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

The ACXSTREAM is composed by a list of zero, one or more ACXELEMENTs added based on the parent ACXCIRCUIT's ACXELEMENTs. By default, ACXELEMENTs are connected in the same order of assembly. An ACXSTREAM is associated with only one ACXCIRCUIT. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RealTime (RT) stream objects used by streaming circuits.

An audio endpoint is a collection of one or more audio circuits (ACXCIRCUIT objects) which are assembled to create a complete audio path. An ACX driver normally creates audio circuits for different audio endpoints, although ACX doesn’t prohibit circuits created by the same driver to be part of the same audio endpoint’s collection, as long as they belong to a different device stack. An audio endpoint is a collection of audio circuits created by the same or different audio drivers. An audio endpoint must have at least one circuit. This minimal configuration corresponds to the legacy PortCls/KS audio filter. An audio endpoint’s circuit collection may contain static circuits, dynamic circuits, or a combination of both.


### Example

Example usage is shown below.

```cpp
    
    //
    // Assign stream callbacks
    //
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPrepareHardware     = EvtStreamPrepareHardware;
    streamCallbacks.EvtAcxStreamReleaseHardware     = EvtStreamReleaseHardware;
    streamCallbacks.EvtAcxStreamRun                 = EvtStreamRun;
    streamCallbacks.EvtAcxStreamPause               = EvtStreamPause;
    streamCallbacks.EvtAcxStreamAssignDrmContentId  = EvtStreamAssignDrmContentId;
        
    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);
    
    //
    // Create the stream.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, STREAM_CONTEXT);
    attributes.EvtCleanupCallback = EvtStreamContextCleanup;
    attributes.EvtDestroyCallback = EvtStreamDestroy;
    status = AcxStreamCreate(Device, Circuit, &attributes, &StreamInit, &stream);
```



## -see-also

[acxstreams.h header](index.md)

