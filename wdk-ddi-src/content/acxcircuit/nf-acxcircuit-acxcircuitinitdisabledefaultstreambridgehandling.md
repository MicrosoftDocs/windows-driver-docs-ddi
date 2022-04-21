---
UID: NF:acxcircuit.AcxCircuitInitDisableDefaultStreamBridgeHandling
tech.root: audio
title: AcxCircuitInitDisableDefaultStreamBridgeHandling
ms.date: 08/17/2021
targetos: Windows
description: The AcxCircuitInitDisableDefaultStreamBridgeHandling function disables the default stream bridge handling when new circuits are initialized. 
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
 - AcxCircuitInitDisableDefaultStreamBridgeHandling
f1_keywords:
 - AcxCircuitInitDisableDefaultStreamBridgeHandling
 - acxcircuit/AcxCircuitInitDisableDefaultStreamBridgeHandling
dev_langs:
 - c++
---

## -description

The AcxCircuitInitDisableDefaultStreamBridgeHandling function disables the default stream bridge handling when new circuits are initialized. 

TBD - Is it normally true that: The create stream handler will add Stream Bridge
to support Object-bag forwarding??? 

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -remarks

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

## -see-also

[acxcircuit.h header](index.md)

TBD - Please review this topic