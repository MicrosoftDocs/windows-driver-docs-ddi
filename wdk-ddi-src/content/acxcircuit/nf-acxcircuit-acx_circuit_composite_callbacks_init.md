---
UID: NF:acxcircuit.ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT
tech.root: audio
title: ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT
ms.date: 01/31/2022
targetos: Windows
description: The ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT function initializes a ACX_CIRCUIT_COMPOSITE_CALLBACKS structure. 
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
 - ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT
f1_keywords:
 - ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT
 - acxcircuit/ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT function initializes a [ACX_CIRCUIT_COMPOSITE_CALLBACKS structure](ns-acxcircuit-acx_circuit_composite_callbacks.md). No inputs are used with this function.

## -parameters

### -param CompositeCallbacks

A pointer to an initialized [ACX_CIRCUIT_COMPOSITE_CALLBACKS structure](ns-acxcircuit-acx_circuit_composite_callbacks.md).


## -remarks

### Example

Example usage is shown below.

```cpp
    // Assign the circuit's composite callbacks.
    //
    {
        ACX_CIRCUIT_COMPOSITE_CALLBACKS compositeCallbacks;
        ACX_CIRCUIT_COMPOSITE_CALLBACKS_INIT(&compositeCallbacks);
        compositeCallbacks.EvtAcxCircuitCompositeCircuitInitialize = CodecR_EvtCircuitCompositeCircuitInitialize;
        compositeCallbacks.EvtAcxCircuitCompositeInitialize = CodecR_EvtCircuitCompositeInitialize;
        AcxCircuitInitSetAcxCircuitCompositeCallbacks(CircuitInit, &compositeCallbacks);
    }
```

## -see-also

[acxcircuit.h header](index.md)

