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

AcxRtStreamCreate creates an ACX RTStream that is used to TBD and TBD.


## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that has/is TBD been TBD.

### -param Circuit

And [ACXCIRCUT]() object (DocsTeam - need link to ACX Object Summary topic) that will be TBD.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to TBD. 

### -param Config

An [ACXSTREAM_INIT]() (DocsTeam - need link to ACX Object Summary topic) Config structure TBD.

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example initialization  is shown below.

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

