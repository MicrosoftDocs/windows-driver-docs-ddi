---
UID: NF:acxstreams.AcxStreamBridgeAddStream
tech.root: audio
title: AcxStreamBridgeAddStream
ms.date: 07/21/2021
targetos: Windows
description: The AcxStreamBridgeAddStream function adds an existing stream to an existing bridge. This function is located in the acxstream header.
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
 - AcxStreamBridgeAddStream
f1_keywords:
 - AcxStreamBridgeAddStream
 - acxstreams/AcxStreamBridgeAddStream
dev_langs:
 - c++
---

## -description

The AcxStreamBridgeAddStream function adds an existing ACXSTREAM to an existing ACXSTREAMBRIDGE. (DocsTeam - need link to ACX Object Summary topics)

## -parameters

### -param Bridge

An [ACXSTREAMBRIDGE] object (DocsTeam - need link to ACX Object Summary topic) is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments. This object is only used in a multi-circuit (audio composite) scenario.

### -param Stream

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Drivers call AcxStreamBridgeAddStream in these scenarios:

(a) drivers want to manually select the ACXSTREAMBRIDGE to use for the current ACXSTREAM. 

(b) drivers (and their hardware requirements) have a need for the downlevel ACXCIRCUITs, i.e., the circuits closer to the device bridge pin, to take action before upper level ACXCIRCUITs take action.

(c) drivers need to take action before and after the downlevel ACXCIRCUITs.

For a AcxStreamBridgeMux type, only one downlevel ACXSTREAM is created independently of the number of input ACXSTREAMs added to this bridge. This means that the output ACXSTREAM (which for the local circuit the stream is represented with an ACXTARGETSTREAM), is only created for the first ACXSTREAM added to the ACXSTREAMBRIDGE. Any additional input ACXSTREAMs, just take a reference to this existing ACXTARGETSTREAM.

For a AcxSTreamBridgeMux type, the output ACXTARGETSTREAM is removed when the last input ACXSTREAM is removed from the ACXSTREAMBRIDGE with AcxStreamBridgeRemoveStream.

### Example

Example usage is shown below. Error handling code is not shown.

```cpp
        status = AcxStreamBridgeCreate(Circuit, &attributes, &bridgeCfg, &bridge);

        // Pin ID 1 is the bridge pin in this example.
        bridgePin = AcxCircuitGetPinById(Circuit, 1);
        
        status = AcxPinAddStreamBridges(bridgePin, &bridge, 1);

        status = AcxStreamBridgeAddStream(bridge, stream);

```

## -see-also

[acxstreams.h header](index.md)

READY2GO

EDITCOMPLETE