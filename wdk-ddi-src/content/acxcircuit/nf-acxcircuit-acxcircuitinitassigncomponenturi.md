---
UID: NF:acxcircuit.AcxCircuitInitAssignComponentUri
tech.root: audio
title: AcxCircuitInitAssignComponentUri
ms.date: 08/17/2021
targetos: Windows
description: The AcxCircuitInitAssignComponentUri function assigns a ComponentUri that will be used for the circuit initialization.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxCircuitInitAssignComponentUri
f1_keywords:
 - AcxCircuitInitAssignComponentUri
 - acxcircuit/AcxCircuitInitAssignComponentUri
dev_langs:
 - c++
---

## -description

The AcxCircuitInitAssignComponentUri function assigns a ComponentUri that will be used for the circuit initialization.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param ComponentUri

A unicode string describes the component that is used as a URI to TBD identify it to TBD.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
DECLARE_CONST_UNICODE_STRING(CODEC_CIRCUIT_CAPTURE_URI, 
    L"acx:test:acxcodectestdriver:codec0:circuit0:microphone0");

    // Get a CircuitInit structure.
    //
    circuitInit = AcxCircuitInitAllocate(Device);

    //
    // Add circuit identifiers.
    //
    status = AcxCircuitInitAssignComponentUri(circuitInit, &CODEC_CIRCUIT_CAPTURE_URI);

```

## -see-also

[acxcircuit.h header](index.md)

