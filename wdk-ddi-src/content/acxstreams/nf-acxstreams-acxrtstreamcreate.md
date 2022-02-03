---
UID: NF:acxstreams.AcxRtStreamCreate
tech.root: audio
title: AcxRtStreamCreate
ms.date: 07/09/2021
targetos: Windows
description: AcxRtStreamCreate creates an ACX RTStream that is used to TBD and TBD
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

AcxRtStreamCreate creates an ACX RTStream audio stream.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT and its' stream. 

### -param Circuit

And *ACXCIRCUIT* object that will be created (???TBD). For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object’s values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An *ACXSTREAM_INIT* Config structure that defines the initialization of the stream. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM Object that represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example Rt stream creation is shown below.

```cpp
//
// Create the stream.
//
WDF_OBJECT_ATTRIBUTES attributes;
ACXSTREAM stream;
WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, DSP_STREAM_CONTEXT);
attributes.EvtDestroyCallback = Dsp_EvtStreamDestroy;
status = AcxRtStreamCreate(Device, Circuit, &attributes, &StreamInit, &stream);
```

## -see-also

[acxstreams.h header](index.md)

