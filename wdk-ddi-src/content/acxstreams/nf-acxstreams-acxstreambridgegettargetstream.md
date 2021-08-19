---
UID: NF:acxstreams.AcxStreamBridgeGetTargetStream
tech.root: audio
title: AcxStreamBridgeGetTargetStream
ms.date: 07/12/2021
targetos: Windows
description: The AcxStreamBridgeGetTargetStream function gets the stream associated with a specific ACXSTREAMBRIDGE object. 
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
 - AcxStreamBridgeGetTargetStream
f1_keywords:
 - AcxStreamBridgeGetTargetStream
 - acxstreams/AcxStreamBridgeGetTargetStream
dev_langs:
 - c++
---

## -description

The AcxStreamBridgeGetTargetStream function gets the [ACXTARGETSTREAM] object (DocsTeam - need link to ACX Object Summary topic) associated with the input [ACXSTREAM] object (DocsTeam - need link to ACX Object Summary topic) on the specified [ACXSTREAMBRIDGE] object (DocsTeam - need link to ACX Object Summary topic). 

## -parameters

### -param Bridge

An [ACXSTREAMBRIDGE] object (DocsTeam - need link to ACX Object Summary topic) handle.

### -param Stream

An [ACXSTREAM] object (DocTeam - need link to ACX Object Summary topic) handle.

[EGI-START]: Please move these two section to ACXSTREAM topic.
An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.
[EGI-END]

## -returns

An [ACXTARGETSTREAM] object (DocsTeam - need link to ACX Object Summary topic) handle.

## -remarks

An [ACXSTREAMBRIDGE] object (DocsTeam - need link to ACX Object Summary topic) is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments.  This object is only used in a multi-circuit (audio composite) scenario.

This DDI can only be called from the driver's input stream property handler context. The caller invokes this DDI to manually send I/O to the out-stream of this stream-bridge object. 

The returned target stream is only valid in the context of the input stream property handler. Note that the target stream may be already busy sending other I/O (such as state change) as directed by other ks property stream operations.


### Example

Example usage is shown below.

```cpp
    status = AcxStreamBridgeAddStream(bridge, stream);

    targetStream = AcxStreamBridgeGetTargetStream(bridge, stream);
```


## -see-also

[acxstreams.h header](index.md)

