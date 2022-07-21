---
UID: NS:acxcircuit._ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
tech.root: audio
title: ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
ms.date: 09/30/2021
targetos: Windows
description: The ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure contains pointers to an ACXFACTORYCIRCUITs Plug and Play and power event callback functions.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS, *PACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - _ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - PACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
f1_keywords:
 - _ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - acxcircuit/_ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - PACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - acxcircuit/PACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
 - acxcircuit/ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS** structure contains pointers to an ACXFACTORYCIRCUIT's Plug and Play and power event callback functions.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field EvtAcxFactoryCircuitPrepareHardware

A pointer to the driver's [ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE callback](nc-acxcircuit-evt_acx_factory_circuit_prepare_hardware.md) event callback function, or NULL.  

### -field EvtAcxFactoryCircuitReleaseHardware
A pointer to the driver's [ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback](nc-acxcircuit-evt_acx_factory_circuit_release_hardware.md) event callback function, or NULL.

### -field EvtAcxFactoryCircuitPowerUp
A pointer to the [ACX_FACTORY_CIRCUIT_POWER_UP callback](nc-acxcircuit-evt_acx_factory_circuit_power_up.md) event callback function, or NULL.

### -field EvtAcxFactoryCircuitPowerDown
A pointer to the [ACX_FACTORY_CIRCUIT_POWER_DOWN callback](nc-acxcircuit-evt_acx_factory_circuit_power_down.md) event callback function, or NULL. 

## -remarks

The ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure is used as input to the [AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks](nf-acxcircuit-acxfactorycircuitinitsetacxcircuitpnppowercallbacks.md) method.

Your driver should initialize its ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS structure by calling the [ACX_FACTORY_CIRCUIT_PNPPOWER_CALLBACKS_INIT](nf-acxcircuit-acx_factory_circuit_pnppower_callbacks_init.md) function.

### Example

Example usage is shown below.

```cpp
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

[AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks](nf-acxcircuit-acxfactorycircuitinitsetacxcircuitpnppowercallbacks.md) 

READY2GO

EDITCOMPLETE