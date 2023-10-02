---
UID: NF:acxcircuit.AcxCircuitInitDisableDefaultStreamBridgeHandling
tech.root: audio
title: AcxCircuitInitDisableDefaultStreamBridgeHandling
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitInitDisableDefaultStreamBridgeHandling function disables the ACX default stream bridge handling in a multi-circuit environment.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - AcxCircuitInitDisableDefaultStreamBridgeHandling
f1_keywords:
 - AcxCircuitInitDisableDefaultStreamBridgeHandling
 - acxcircuit/AcxCircuitInitDisableDefaultStreamBridgeHandling
dev_langs:
 - c++
---

## -description

The **AcxCircuitInitDisableDefaultStreamBridgeHandling** function disables the ACX default stream bridge handling in a multi-circuit environment.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -remarks

When the driver invokes this method and the stream doesn't have an associated ACXSTREAMBRIDGE, ACX will not attempt to create a default stream bridge to forward the stream and its states to the next circuit.

This function doesn't have any effect when called on a single-circuit endpoint or on the last circuit of a multi-circuit endpoint.

### Example

Example usage is shown below.

```cpp
    //
    // Get a CircuitInit structure.
    //
    PACXCIRCUIT_INIT circuitInit = NULL;
    circuitInit = AcxCircuitInitAllocate(Device);

    //
    // Disable default Stream Bridge handling in ACX
    // Create stream handler will add Stream Bridge
    // to support Object-bag forwarding
    //
    AcxCircuitInitDisableDefaultStreamBridgeHandling(circuitInit);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
