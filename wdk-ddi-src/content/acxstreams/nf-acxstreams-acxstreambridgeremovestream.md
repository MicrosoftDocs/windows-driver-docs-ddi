---
UID: NF:acxstreams.AcxStreamBridgeRemoveStream
tech.root: audio
title: AcxStreamBridgeRemoveStream
ms.date: 07/21/2021
targetos: Windows
description: The AcxStreamBridgeRemoveStream function removes the specified stream from the the associated ACXSTREAMBRIDGE object. 
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
 - AcxStreamBridgeRemoveStream
f1_keywords:
 - AcxStreamBridgeRemoveStream
 - acxstreams/AcxStreamBridgeRemoveStream
dev_langs:
 - c++
---

## -description

The AcxStreamBridgeRemoveStream function removes the specified ACXSTREAM from the [ACXSTREAMBRIDGE] object (DocsTeam - need link to ACX Object Summary topic). 

## -parameters

### -param Bridge

An [ACXSTREAMBRIDGE] object (DocsTeam - need link to ACX Object Summary topic) is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments. This object is only used in a multi-circuit (audio composite) scenario.

### -param Stream

A handle to the ACXSTREAM Object to be removed from the ACXSTREAMBRIDGE.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

This DDI can only be called from the driver's stream cleanup handler context. The caller invokes this DDI to manually dissociate an input ACXSTREAM from the specified ACXSTREAMBRIDGE object.

Drivers call AcxStreamBridgeRemoveStream in these scenarios:

(a) drivers want to manually remove the ACXSTREAM from the ACXSTREAMBRIDGE. 

(b) drivers (and thier h/w requirements) need for the upper level ACXSTREAMs i.e., the circuit streams closer to the streaming bridge pin, to take action before downlevel ACXSTREAMs.

(c) drivers need to take action before and after the downlevel ACXSTREAM goes away.

For a AcxStreamBridgeMux type, only one downlevel ACXSTREAM is created independently of the number of input ACXSTREAMs added to this bridge. This means that the output ACXSTREAM (which for the local circuit the stream is represented with an ACXTARGETSTREAM), is only created for the first ACXSTREAM added to the ACXSTREAMBRIDGE. Any additional input ACXSTREAMs just take a reference to this existing ACXTARGETSTREAM.

For a AcxStreamBridgeMux type, the output ACXTARGETSTREAM is removed when the last input ACXSTREAM is removed from the ACXSTREAMBRIDGE with AcxStreamBridgeRemoveStream.

### Example

Example usage is shown below.

```cpp
    status = AcxStreamBridgeAddStream(bridge, stream);

    // Get I/O target to send I/O to the target stream.
    targetStream = AcxStreamBridgeGetTargetStream(bridge, stream);
 
    // Target stream is closed if this was last input ACXSTREAM removed.
    status = AcxStreamBridgeRemoveStream(bridge, stream);
```


## -see-also

[acxstreams.h header](index.md)


READY2GO

EDITCOMPLETE