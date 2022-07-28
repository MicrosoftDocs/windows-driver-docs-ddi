---
UID: NF:acxcircuit.AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks
tech.root: audio
title: AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks
ms.date: 07/28/2022
targetos: Windows
description: The AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks function sets the driver's PNP callbacks for the ACXFACTORYCIRCUIT.
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
 - AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks
f1_keywords:
 - AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks
 - acxcircuit/AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks function sets the driver's PNP callbacks for the ACXFACTORYCIRCUIT.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.

Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param EvtPnpPowerCallbacks

An [ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS](ns-acxcircuit-acx_factory_circuit_pnppower_callbacks.md) power callbacks structure that defines the callbacks.

## -remarks

NOTE: At this time this DDI is not supported. Do not use it at this time.

Before calling AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks, your driver should initialize its ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure by calling [ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT](nf-acxcircuit-acx_factory_circuit_pnppower_callbacks_init.md). The ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure is used as input to the [AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks method](nf-acxcircuit-acxfactorycircuitinitsetacxcircuitpnppowercallbacks.md).

### Example

Example usage is shown below.

```cpp
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Assign the factory circuit's pnp-power callbacks.
    //
    ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS powerCallbacks;
    ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT(&powerCallbacks);
    powerCallbacks.EvtAcxFactoryCircuitPowerUp = EvtFactoryCircuitPowerUp;
    powerCallbacks.EvtAcxFactoryCircuitPowerDown = EvtFactoryCircuitPowerDown;
    AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks(factoryInit, &powerCallbacks);
```

## -see-also

- [acxcircuit.h header](index.md)

