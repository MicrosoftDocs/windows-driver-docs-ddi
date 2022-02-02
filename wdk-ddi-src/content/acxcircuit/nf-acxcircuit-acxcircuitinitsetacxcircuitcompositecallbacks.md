---
UID: NF:acxcircuit.AcxCircuitInitSetAcxCircuitCompositeCallbacks
tech.root: audio
title: AcxCircuitInitSetAcxCircuitCompositeCallbacks
ms.date: 08/18/2021
targetos: Windows
description: The AcxCircuitInitSetAcxCircuitCompositeCallbacks function sets the composite callbacks for and ACX Circuit initialization process.
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
 - AcxCircuitInitSetAcxCircuitCompositeCallbacks
f1_keywords:
 - AcxCircuitInitSetAcxCircuitCompositeCallbacks
 - acxcircuit/AcxCircuitInitSetAcxCircuitCompositeCallbacks
dev_langs:
 - c++
---

## -description

The AcxCircuitInitSetAcxCircuitCompositeCallbacks function sets the composite callbacks for and ACX Circuit initialization process.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param EvtCompositeCallbacks

A pointer to an initialized [ACX_CIRCUIT_COMPOSITE_CALLBACKS structure](ns-acxcircuit-acx_circuit_composite_callbacks.md) that contains the callbacks to be used for the circuit.


## -remarks

This function does not return a value.

### Example

Example usage is shown below.

```cpp
    //
    // Assign the circuit's composite callbacks.
    //
    {
        ACX_CIRCUIT_COMPOSITE_CALLBACKS compositeCallbacks;
        ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT(&compositeCallbacks);
        compositeCallbacks.EvtAcxCircuitCompositeCircuitInitialize = CodecR_EvtCircuitCompositeCircuitInitialize;
        compositeCallbacks.EvtAcxCircuitCompositeInitialize = CodecR_EvtCircuitCompositeInitialize;
        compositeCallbacks.EvtAcxCircuitCompositeDeinitialize = CodecR_EvtCircuitCompositeDeinitialize;
        AcxCircuitInitSetAcxCircuitCompositeCallbacks(circuitInit, &compositeCallbacks);
    }
```

## -see-also

[acxcircuit.h header](index.md)

