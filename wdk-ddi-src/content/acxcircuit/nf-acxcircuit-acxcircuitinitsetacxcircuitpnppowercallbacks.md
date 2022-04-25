---
UID: NF:acxcircuit.AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
tech.root: audio
title: AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
ms.date: 02/01/2022
targetos: Windows
description: The AcxCircuitInitSetAcxCircuitPnpPowerCallbacks function sets the composite callbacks for an ACX Circuit initialization process.
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
 - AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
f1_keywords:
 - AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
 - acxcircuit/AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
dev_langs:
 - c++
---

## -description

The AcxCircuitInitSetAcxCircuitPnpPowerCallbacks function sets the composite callbacks for an ACX Circuit initialization process.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param EvtPnpPowerCallbacks

An [ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS](ns-acxcircuit-acx_factory_circuit_pnppower_callbacks.md) PnP power callbacks structure that defines the callbacks.

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Assign the circuit's pnp-power callbacks.
    //
    ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
    powerCallbacks.EvtAcxCircuitPowerUp = CodecR_EvtCircuitPowerUp;
    powerCallbacks.EvtAcxCircuitPowerDown = CodecR_EvtCircuitPowerDown;
    AcxCircuitInitSetAcxCircuitPnpPowerCallbacks(circuitInit, &powerCallbacks);
```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic