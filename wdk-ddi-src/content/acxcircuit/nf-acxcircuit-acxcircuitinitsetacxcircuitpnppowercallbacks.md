---
UID: NF:acxcircuit.AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
tech.root: audio
title: AcxCircuitInitSetAcxCircuitPnpPowerCallbacks
ms.date: 07/28/2022
targetos: Windows
description: The AcxCircuitInitSetAcxCircuitPnpPowerCallbacks function sets the driver's PNP callbacks for the ACXCIRCUIT.
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

The **AcxCircuitInitSetAcxCircuitPnpPowerCallbacks** function sets the driver's PNP callbacks for the ACXCIRCUIT.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param EvtPnpPowerCallbacks

An [ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS](ns-acxcircuit-acx_factory_circuit_pnppower_callbacks.md) PnP power callbacks structure that defines the callbacks.

## -remarks

Before calling AcxCircuitInitSetAcxCircuitPnpPowerCallbacks, your driver should initialize its ACX_CIRCUIT_PNPPOWER_CALLBACKS structure by calling [ACX_CIRCUIT_PNPPOWER_CALLBACKS_INIT](nf-acxcircuit-acx_circuit_pnppower_callbacks_init.md). The ACX_CIRCUIT_PNPPOWER_CALLBACKS structure is used as input to the [AcxCircuitInitSetAcxCircuitPnpPowerCallbacks method](nf-acxcircuit-acxcircuitinitsetacxcircuitpnppowercallbacks.md).

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

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)

