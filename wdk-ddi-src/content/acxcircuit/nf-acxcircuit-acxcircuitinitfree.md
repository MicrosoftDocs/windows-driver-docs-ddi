---
UID: NF:acxcircuit.AcxCircuitInitFree
tech.root: audio
title: AcxCircuitInitFree
ms.date: 08/18/2021
targetos: Windows
description: The AcxCircuitInitFree function frees the circuit (TBD - at the end of the initialization process?).
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
 - AcxCircuitInitFree
f1_keywords:
 - AcxCircuitInitFree
 - acxcircuit/AcxCircuitInitFree
dev_langs:
 - c++
---

## -description

The AcxCircuitInitFree function frees the circuit initialization object and the TBD??? associated with the circuit.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -remarks

This function does not return a value.

### Example

Example usage is shown below.

```cpp

    //
    // Get a CircuitInit structure.
    //
    PACXCIRCUIT_INIT circuitInit = NULL;
    circuitInit = AcxCircuitInitAllocate(Device);

// Later in the code on an exit close down process...

exit:
    if (!NT_SUCCESS(status))
    {
        if (circuitInit)
        {
            AcxCircuitInitFree(circuitInit);
        }
    }

```

## -see-also

[acxcircuit.h header](index.md)

TBD - Please review this topic