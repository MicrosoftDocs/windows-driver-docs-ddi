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

The AcxStreamBridgeGetTargetStream function gets the ACXTARGETSTREAM object associated with the input ACXSTREAM object on the specified ACXSTREAMBRIDGE object. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

## -parameters

### -param Bridge

An [ACXSTREAMBRIDGE] object handle.

### -param Stream

An [ACXSTREAM] object handle.

An ACXSTREAM object represents an audio stream created by a circuit. 

## -returns

An ACXTARGETSTREAM object handle.

## -remarks

An ACXSTREAMBRIDGE object is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments.  This object is only used in a multi-circuit (audio composite) scenario.

This DDI can only be called from the driver's input stream property handler context. The caller invokes this DDI to manually send I/O to the out-stream of this stream-bridge object. 

The returned target stream is only valid in the context of the input stream property handler. Note that the target stream may be already busy sending other I/O (such as state change) as directed by other ks property stream operations.


### Example

Example usage is shown below.

```cpp
    status = AcxStreamBridgeAddStream(bridge, stream);

    targetStream = AcxStreamBridgeGetTargetStream(bridge, stream);
```


## -see-also

- [acxstreams.h header](index.md)

READY2GO